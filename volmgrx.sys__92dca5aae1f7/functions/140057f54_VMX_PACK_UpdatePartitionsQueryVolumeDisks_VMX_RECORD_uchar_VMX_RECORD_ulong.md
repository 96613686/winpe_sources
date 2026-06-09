# VMX_PACK::UpdatePartitionsQueryVolumeDisks(VMX_RECORD *,uchar,VMX_RECORD * * *,ulong *)

- ea: `0x140057f54`
- end: `0x140058114`
- name: `?UpdatePartitionsQueryVolumeDisks@VMX_PACK@@QEAAJPEAVVMX_RECORD@@EPEAPEAPEAV2@PEAK@Z`
- size: `448`
- prototype: `__int64 __fastcall(VMX_PACK *this, struct VMX_RECORD *, char, struct VMX_RECORD ***, unsigned int *)`
- caller_count: `5`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1400362a8`
- `0x140036bac`
- `0x140036e70`
- `0x140037fe4`
- `0x14003bd90`

## callees

- `0x1400099d8`
- `0x140009fcc`
- `0x140057f54`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140057f9a`
- `ntoskrnl!ExAllocatePool2` at `0x140057f9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005809f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400580f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005809f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400580f0`

## pseudocode

```c
__int64 __fastcall VMX_PACK::UpdatePartitionsQueryVolumeDisks(
        VMX_PACK *this,
        struct VMX_RECORD *a2,
        char a3,
        struct VMX_RECORD ***a4,
        unsigned int *a5)
{
  __int64 v6; // rax
  __int64 v8; // rsi
  void *Pool2; // r8
  VMX_NOTIFICATION_QUEUE *v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // rdx

  v6 = *((_WORD *)a2 + 32) & 1;
  *a4 = 0;
  *a5 = 0;
  v8 = *((_QWORD *)a2 + v6 + 5);
  Pool2 = (void *)ExAllocatePool2(258, 8LL * *(unsigned int *)(v8 + 160), 538996054);
  if ( Pool2 )
  {
    v14 = *(_QWORD *)(v8 + 264);
    v15 = 0;
    while ( 1 )
    {
      if ( !v14 )
      {
        if ( !(_DWORD)v15 )
        {
          ExFreePoolWithTag(Pool2, 0);
          Pool2 = 0;
        }
        *a4 = (struct VMX_RECORD **)Pool2;
        *a5 = v15;
        return 0;
      }
      v16 = *(_QWORD *)(v14 + 8LL * (*(_WORD *)(v14 + 64) & 1) + 40);
      if ( *(_BYTE *)(v16 + 87) == 2 && *(_DWORD *)(v16 + 92) == 1 )
      {
        *((_QWORD *)Pool2 + v15) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v16 + 152)
                                                         + 8LL * (*(_WORD *)(*(_QWORD *)(v16 + 152) + 64LL) & 1)
                                                         + 40)
                                             + 152LL);
        v15 = (unsigned int)(v15 + 1);
      }
      else if ( !a3 )
      {
        ExFreePoolWithTag(Pool2, 0);
        v10 = WPP_GLOBAL_Control;
        v11 = -1070071744;
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          v12 = 104;
          goto LABEL_11;
        }
        return v11;
      }
      v14 = *(_QWORD *)(v16 + 144);
    }
  }
  if ( !a3 )
  {
    v10 = WPP_GLOBAL_Control;
    v11 = -1073741670;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v12 = 103;
LABEL_11:
      WPP_SF_d(*((_QWORD *)v10 + 3), v12, WPP_b525482092043ba595507d12d78e6f73_Traceguids, v11);
    }
    return v11;
  }
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 102, WPP_b525482092043ba595507d12d78e6f73_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140057f54  push    rbx
0x140057f56  push    rsi
0x140057f57  push    rdi
0x140057f58  push    r14
0x140057f5a  push    r15
0x140057f5c  sub     rsp, 20h
0x140057f60  movzx   eax, word ptr [rdx+40h]
0x140057f64  mov     dil, r8b
0x140057f67  mov     r15, [rsp+48h+arg_20]
0x140057f6c  and     eax, 1
0x140057f6f  mov     qword ptr [r9], 0
0x140057f76  mov     ecx, 102h
0x140057f7b  mov     r8d, 20206D56h
0x140057f81  mov     r14, r9
0x140057f84  mov     dword ptr [r15], 0
0x140057f8b  mov     rsi, [rdx+rax*8+28h]
0x140057f90  mov     edx, [rsi+0A0h]
0x140057f96  shl     rdx, 3
0x140057f9a  call    cs:__imp_ExAllocatePool2
0x140057fa1  nop     dword ptr [rax+rax+00h]
0x140057fa6  mov     r8, rax
0x140057fa9  test    rax, rax
0x140057fac  jnz     loc_140058040
0x140057fb2  test    dil, dil
0x140057fb5  jz      short loc_140057FFC
0x140057fb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140057fbe  lea     rax, WPP_GLOBAL_Control
0x140057fc5  cmp     rcx, rax
0x140057fc8  jz      loc_140058105
0x140057fce  mov     eax, [rcx+2Ch]
0x140057fd1  test    al, 8
0x140057fd3  jz      loc_140058105
0x140057fd9  cmp     byte ptr [rcx+29h], 3
0x140057fdd  jb      loc_140058105
0x140057fe3  mov     rcx, [rcx+18h]
0x140057fe7  lea     edx, [r8+66h]
0x140057feb  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x140057ff2  call    WPP_SF_
0x140057ff7  jmp     loc_140058105
0x140057ffc  mov     rcx, cs:WPP_GLOBAL_Control
0x140058003  lea     rax, WPP_GLOBAL_Control
0x14005800a  mov     ebx, 0C000009Ah
0x14005800f  cmp     rcx, rax
0x140058012  jz      short loc_140058039
0x140058014  mov     eax, [rcx+2Ch]
0x140058017  test    al, 8
0x140058019  jz      short loc_140058039
0x14005801b  cmp     byte ptr [rcx+29h], 2
0x14005801f  jb      short loc_140058039
0x140058021  mov     edx, 67h ; 'g'
0x140058026  mov     rcx, [rcx+18h]
0x14005802a  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x140058031  mov     r9d, ebx
0x140058034  call    WPP_SF_d
0x140058039  mov     eax, ebx
0x14005803b  jmp     loc_140058107
0x140058040  mov     rcx, [rsi+108h]
0x140058047  xor     ebx, ebx
0x140058049  test    rcx, rcx
0x14005804c  jz      loc_1400580E7
0x140058052  movzx   eax, word ptr [rcx+40h]
0x140058056  and     eax, 1
0x140058059  mov     rdx, [rcx+rax*8+28h]
0x14005805e  cmp     byte ptr [rdx+57h], 2
0x140058062  jnz     short loc_14005808C
0x140058064  cmp     dword ptr [rdx+5Ch], 1
0x140058068  jnz     short loc_14005808C
0x14005806a  mov     rcx, [rdx+98h]
0x140058071  movzx   eax, word ptr [rcx+40h]
0x140058075  and     eax, 1
0x140058078  mov     rax, [rcx+rax*8+28h]
0x14005807d  mov     rax, [rax+98h]
0x140058084  mov     [r8+rbx*8], rax
0x140058088  inc     ebx
0x14005808a  jmp     short loc_140058091
0x14005808c  test    dil, dil
0x14005808f  jz      short loc_14005809A
0x140058091  mov     rcx, [rdx+90h]
0x140058098  jmp     short loc_140058049
0x14005809a  xor     edx, edx; Tag
0x14005809c  mov     rcx, r8; P
0x14005809f  call    cs:__imp_ExFreePoolWithTag
0x1400580a6  nop     dword ptr [rax+rax+00h]
0x1400580ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400580b2  lea     rax, WPP_GLOBAL_Control
0x1400580b9  mov     ebx, 0C0380040h
0x1400580be  cmp     rcx, rax
0x1400580c1  jz      loc_140058039
0x1400580c7  mov     edx, [rcx+2Ch]
0x1400580ca  test    dl, 8
0x1400580cd  jz      loc_140058039
0x1400580d3  cmp     byte ptr [rcx+29h], 2
0x1400580d7  jb      loc_140058039
0x1400580dd  mov     edx, 68h ; 'h'
0x1400580e2  jmp     loc_140058026
0x1400580e7  test    ebx, ebx
0x1400580e9  jnz     short loc_1400580FF
0x1400580eb  xor     edx, edx; Tag
0x1400580ed  mov     rcx, r8; P
0x1400580f0  call    cs:__imp_ExFreePoolWithTag
0x1400580f7  nop     dword ptr [rax+rax+00h]
0x1400580fc  xor     r8d, r8d
0x1400580ff  mov     [r14], r8
0x140058102  mov     [r15], ebx
0x140058105  xor     eax, eax
0x140058107  add     rsp, 20h
0x14005810b  pop     r15
0x14005810d  pop     r14
0x14005810f  pop     rdi
0x140058110  pop     rsi
0x140058111  pop     rbx
0x140058112  retn
```
