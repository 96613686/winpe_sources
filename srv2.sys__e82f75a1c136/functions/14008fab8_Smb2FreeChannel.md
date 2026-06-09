# Smb2FreeChannel

- ea: `0x14008fab8`
- end: `0x14008fb96`
- name: `Smb2FreeChannel`
- size: `222`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140013990`

## callees

- `0x14000aab4`
- `0x14000ae60`
- `0x140013920`
- `0x14008fab8`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14008fb22`
- `ntoskrnl!ExDeleteResourceLite` at `0x14008fb22`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008fb33`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008fb33`
- `srvnet!SrvNetDecrementConnectionActiveCount` at `0x14008faf9`
- `srvnet!SrvNetDecrementConnectionActiveCount` at `0x14008faf9`
- `ksecdd!BCryptDestroyHash` at `0x14008fb69`
- `ksecdd!BCryptDestroyHash` at `0x14008fb69`

## pseudocode

```c
void __fastcall Smb2FreeChannel(char *P)
{
  void *v2; // rcx
  _QWORD *v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // rcx

  v2 = (void *)*((_QWORD *)P + 23);
  v3 = P + 64;
  if ( v2 )
  {
    if ( *(void **)(*v3 + 224LL) != v2 )
      BCryptDestroyHash(v2);
    *((_QWORD *)P + 23) = 0;
    *((_DWORD *)P + 49) = 0;
  }
  v4 = *((_QWORD *)P + 25);
  if ( v4 )
  {
    if ( *(_QWORD *)(*v3 + 240LL) != v4 )
      Smb2DeallocateSigningHashObject(v4);
    *((_DWORD *)P + 48) = 0;
    *((_QWORD *)P + 25) = 0;
  }
  v5 = *((_QWORD *)P + 7);
  if ( v5 )
  {
    SrvNetDecrementConnectionActiveCount(*(_QWORD *)(v5 + 480));
    Srv2DereferenceConnection(*((PVOID *)P + 7));
    *((_QWORD *)P + 7) = 0;
  }
  if ( *v3 )
  {
    Smb2DereferenceSession(*v3);
    *v3 = 0;
  }
  ExDeleteResourceLite((PERESOURCE)(P + 80));
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14008fab8  mov     [rsp+arg_0], rbx
0x14008fabd  push    rdi
0x14008fabe  sub     rsp, 20h
0x14008fac2  mov     rbx, rcx
0x14008fac5  mov     rcx, [rcx+0B8h]; hHash
0x14008facc  lea     rdi, [rbx+40h]
0x14008fad0  test    rcx, rcx
0x14008fad3  jnz     loc_14008FB59
0x14008fad9  mov     rcx, [rbx+0C8h]
0x14008fae0  test    rcx, rcx
0x14008fae3  jnz     loc_14008FB7B
0x14008fae9  mov     rcx, [rbx+38h]
0x14008faed  test    rcx, rcx
0x14008faf0  jz      short loc_14008FB16
0x14008faf2  mov     rcx, [rcx+1E0h]
0x14008faf9  call    cs:__imp_SrvNetDecrementConnectionActiveCount
0x14008fb00  nop     dword ptr [rax+rax+00h]
0x14008fb05  mov     rcx, [rbx+38h]; P
0x14008fb09  call    Srv2DereferenceConnection
0x14008fb0e  mov     qword ptr [rbx+38h], 0
0x14008fb16  mov     rcx, [rdi]
0x14008fb19  test    rcx, rcx
0x14008fb1c  jnz     short loc_14008FB4B
0x14008fb1e  lea     rcx, [rbx+50h]; Resource
0x14008fb22  call    cs:__imp_ExDeleteResourceLite
0x14008fb29  nop     dword ptr [rax+rax+00h]
0x14008fb2e  xor     edx, edx; Tag
0x14008fb30  mov     rcx, rbx; P
0x14008fb33  call    cs:__imp_ExFreePoolWithTag
0x14008fb3a  nop     dword ptr [rax+rax+00h]
0x14008fb3f  mov     rbx, [rsp+28h+arg_0]
0x14008fb44  add     rsp, 20h
0x14008fb48  pop     rdi
0x14008fb49  retn
0x14008fb4b  call    Smb2DereferenceSession
0x14008fb50  mov     qword ptr [rdi], 0
0x14008fb57  jmp     short loc_14008FB1E
0x14008fb59  mov     rax, [rdi]
0x14008fb5c  cmp     [rax+0E0h], rcx
0x14008fb63  jz      loc_14009BBAA
0x14008fb69  call    cs:__imp_BCryptDestroyHash
0x14008fb70  nop     dword ptr [rax+rax+00h]
0x14008fb75  nop
0x14008fb76  jmp     loc_14009BBAA
0x14008fb7b  mov     rax, [rdi]
0x14008fb7e  cmp     [rax+0F0h], rcx
0x14008fb85  jz      loc_14009BBC4
0x14008fb8b  call    Smb2DeallocateSigningHashObject
0x14008fb90  nop
0x14008fb91  jmp     loc_14009BBC4
0x14009bbaa  mov     qword ptr [rbx+0B8h], 0
0x14009bbb5  mov     dword ptr [rbx+0C4h], 0
0x14009bbbf  jmp     loc_14008FAD9
0x14009bbc4  mov     dword ptr [rbx+0C0h], 0
0x14009bbce  mov     qword ptr [rbx+0C8h], 0
0x14009bbd9  jmp     loc_14008FAE9
```
