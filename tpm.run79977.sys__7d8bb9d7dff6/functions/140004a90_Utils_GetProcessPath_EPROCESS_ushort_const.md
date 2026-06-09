# Utils::GetProcessPath(_EPROCESS *,ushort const * *)

- ea: `0x140004a90`
- end: `0x140004bb1`
- name: `?GetProcessPath@Utils@@SAJPEAU_EPROCESS@@PEAPEBG@Z`
- size: `289`
- prototype: `__int64 __fastcall(struct _EPROCESS *, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400038e0`
- `0x140016628`

## callees

- `0x140004a90`
- `0x1400454a0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140004aee`
- `ntoskrnl!ExAllocatePool2` at `0x140004aee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004b80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004b80`
- `ntoskrnl!SeLocateProcessImageName` at `0x140004aab`
- `ntoskrnl!SeLocateProcessImageName` at `0x140004aab`

## pseudocode

```c
__int64 __fastcall Utils::GetProcessPath(struct _EPROCESS *a1, unsigned __int16 **a2)
{
  NTSTATUS v3; // ebx
  unsigned __int64 v4; // rdx
  unsigned __int16 *Pool2; // rax
  unsigned __int16 *v6; // r10
  PUNICODE_STRING v7; // r11
  unsigned __int16 *v8; // r9
  __int64 Length; // rax
  PWSTR Buffer; // rdx
  __int64 v11; // r8
  unsigned __int16 *v12; // rcx
  _UNKNOWN *retaddr; // [rsp+28h] [rbp+0h]
  PUNICODE_STRING pImageFileName; // [rsp+40h] [rbp+18h] BYREF

  pImageFileName = 0;
  v3 = SeLocateProcessImageName(a1, &pImageFileName);
  if ( v3 >= 0 )
  {
    v4 = 2LL * pImageFileName->Length + 18;
    if ( v4 < 2 * (unsigned __int64)pImageFileName->Length + 2 )
      goto LABEL_17;
    Pool2 = (unsigned __int16 *)ExAllocatePool2(257, v4, 1349349460);
    v6 = Pool2;
    if ( Pool2 )
    {
      v6 = Pool2 + 8;
      *(_QWORD *)Pool2 = retaddr;
      *((_QWORD *)Pool2 + 1) = retaddr;
    }
    if ( v6 )
    {
      v7 = pImageFileName;
      v8 = v6;
      Length = pImageFileName->Length;
      Buffer = pImageFileName->Buffer;
      v11 = Length + 1;
      do
      {
        if ( !Length )
          break;
        if ( !*Buffer )
          break;
        *v8++ = *Buffer++;
        --Length;
        --v11;
      }
      while ( v11 );
      v12 = v8 - 1;
      v3 = -2147483643;
      if ( v11 )
      {
        v12 = v8;
        v3 = 0;
      }
      *v12 = 0;
      if ( v11 )
      {
        v3 = 0;
        v6[v7->Length] = 0;
        *a2 = v6;
      }
      else
      {
        TpmFree(v6);
      }
    }
    else
    {
LABEL_17:
      v3 = -1073741670;
    }
  }
  if ( pImageFileName )
    ExFreePoolWithTag(pImageFileName, 0);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140004a90  mov     [rsp+arg_0], rbx
0x140004a95  push    rdi
0x140004a96  sub     rsp, 20h
0x140004a9a  mov     rdi, rdx
0x140004a9d  mov     [rsp+28h+pImageFileName], 0
0x140004aa6  lea     rdx, [rsp+28h+pImageFileName]; pImageFileName
0x140004aab  call    cs:__imp_SeLocateProcessImageName
0x140004ab2  nop     dword ptr [rax+rax+00h]
0x140004ab7  mov     ebx, eax
0x140004ab9  test    eax, eax
0x140004abb  js      loc_140004B74
0x140004ac1  mov     rax, [rsp+28h+pImageFileName]
0x140004ac6  mov     rbx, [rsp+28h]
0x140004acb  movzx   ecx, word ptr [rax]
0x140004ace  lea     rcx, ds:2[rcx*2]
0x140004ad6  lea     rdx, [rcx+10h]
0x140004ada  cmp     rdx, rcx
0x140004add  jb      loc_140004B9A
0x140004ae3  mov     ecx, 101h
0x140004ae8  mov     r8d, 506D7054h
0x140004aee  call    cs:__imp_ExAllocatePool2
0x140004af5  nop     dword ptr [rax+rax+00h]
0x140004afa  mov     r10, rax
0x140004afd  test    rax, rax
0x140004b00  jz      short loc_140004B12
0x140004b02  mov     rcx, [rsp+28h]
0x140004b07  add     r10, 10h
0x140004b0b  mov     [rax], rbx
0x140004b0e  mov     [rax+8], rcx
0x140004b12  test    r10, r10
0x140004b15  jz      loc_140004B9A
0x140004b1b  mov     r11, [rsp+28h+pImageFileName]
0x140004b20  mov     r9, r10
0x140004b23  movzx   eax, word ptr [r11]
0x140004b27  mov     rdx, [r11+8]
0x140004b2b  lea     r8, [rax+1]
0x140004b2f  nop
0x140004b30  test    rax, rax
0x140004b33  jz      short loc_140004B52
0x140004b35  movzx   ecx, word ptr [rdx]
0x140004b38  test    cx, cx
0x140004b3b  jz      short loc_140004B52
0x140004b3d  mov     [r9], cx
0x140004b41  add     rdx, 2
0x140004b45  add     r9, 2
0x140004b49  dec     rax
0x140004b4c  sub     r8, 1
0x140004b50  jnz     short loc_140004B30
0x140004b52  xor     eax, eax
0x140004b54  lea     rcx, [r9-2]
0x140004b58  test    r8, r8
0x140004b5b  mov     ebx, 80000005h
0x140004b60  cmovnz  rcx, r9
0x140004b64  cmovnz  ebx, eax
0x140004b67  mov     [rcx], ax
0x140004b6a  jnz     short loc_140004BA1
0x140004b6c  mov     rcx, r10; void *
0x140004b6f  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x140004b74  mov     rcx, [rsp+28h+pImageFileName]; P
0x140004b79  test    rcx, rcx
0x140004b7c  jz      short loc_140004B8C
0x140004b7e  xor     edx, edx; Tag
0x140004b80  call    cs:__imp_ExFreePoolWithTag
0x140004b87  nop     dword ptr [rax+rax+00h]
0x140004b8c  mov     eax, ebx
0x140004b8e  mov     rbx, [rsp+28h+arg_0]
0x140004b93  add     rsp, 20h
0x140004b97  pop     rdi
0x140004b98  retn
0x140004b9a  mov     ebx, 0C000009Ah
0x140004b9f  jmp     short loc_140004B74
0x140004ba1  movzx   ecx, word ptr [r11]
0x140004ba5  xor     ebx, ebx
0x140004ba7  mov     [r10+rcx*2], ax
0x140004bac  mov     [rdi], r10
0x140004baf  jmp     short loc_140004B74
```
