# CPEnumXWizardControlTask::Next(ulong,_GUID * *,ulong *)

- ea: `0x180029b90`
- end: `0x180029c69`
- name: `?Next@CPEnumXWizardControlTask@@UEAAJKPEAPEAU_GUID@@PEAK@Z`
- size: `217`
- prototype: `int(CPEnumXWizardControlTask *__hidden this, unsigned int, struct _GUID **, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ae04`
- `0x180029b90`
- `0x180032a02`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029c1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029c1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029c33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029c33`

## pseudocode

```c
__int64 __fastcall CPEnumXWizardControlTask::Next(
        CPEnumXWizardControlTask *this,
        unsigned int a2,
        struct _GUID **a3,
        unsigned int *a4)
{
  unsigned int v8; // ebx
  struct _GUID *v10; // rax

  if ( !a3 )
    goto LABEL_4;
  if ( a4 )
  {
    *a4 = 0;
  }
  else if ( a2 != 1 )
  {
LABEL_4:
    v8 = -2147467261;
    goto LABEL_5;
  }
  memset_0(a3, 0, 8LL * a2);
  if ( a2 != 1 )
  {
LABEL_11:
    v8 = 1;
    goto LABEL_5;
  }
  v10 = (struct _GUID *)CoTaskMemAlloc(0x10u);
  if ( !v10 )
  {
    v8 = -2147024882;
    goto LABEL_5;
  }
  if ( *((_DWORD *)this + 16) )
  {
    CoTaskMemFree(v10);
    goto LABEL_11;
  }
  v8 = 0;
  *v10 = *(struct _GUID *)((char *)this + 68);
  *a3 = v10;
  if ( a4 )
    *a4 = 1;
  *((_DWORD *)this + 16) = 1;
LABEL_5:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_c6669d9ac1503cc7874ef834ce866b83_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180029b90  push    rbx
0x180029b92  push    rsi
0x180029b93  push    rdi
0x180029b94  push    r14
0x180029b96  sub     rsp, 28h
0x180029b9a  mov     ebx, edx
0x180029b9c  mov     rdi, r9
0x180029b9f  mov     r14, r8
0x180029ba2  mov     rsi, rcx
0x180029ba5  test    r8, r8
0x180029ba8  jz      short loc_180029BB4
0x180029baa  test    r9, r9
0x180029bad  jnz     short loc_180029BF6
0x180029baf  cmp     ebx, 1
0x180029bb2  jz      short loc_180029BFD
0x180029bb4  mov     ebx, 80004003h
0x180029bb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180029bc0  lea     rax, WPP_GLOBAL_Control
0x180029bc7  cmp     rcx, rax
0x180029bca  jz      short loc_180029BEA
0x180029bcc  test    byte ptr [rcx+1Ch], 10h
0x180029bd0  jz      short loc_180029BEA
0x180029bd2  mov     rcx, [rcx+10h]
0x180029bd6  lea     r8, WPP_c6669d9ac1503cc7874ef834ce866b83_Traceguids
0x180029bdd  mov     edx, 0Ah
0x180029be2  mov     r9d, ebx
0x180029be5  call    WPP_SF_d
0x180029bea  mov     eax, ebx
0x180029bec  add     rsp, 28h
0x180029bf0  pop     r14
0x180029bf2  pop     rdi
0x180029bf3  pop     rsi
0x180029bf4  pop     rbx
0x180029bf5  retn
0x180029bf6  mov     dword ptr [r9], 0
0x180029bfd  mov     r8, rbx
0x180029c00  xor     edx, edx; Val
0x180029c02  shl     r8, 3; Size
0x180029c06  mov     rcx, r14; void *
0x180029c09  call    memset_0
0x180029c0e  cmp     ebx, 1
0x180029c11  jz      short loc_180029C1A
0x180029c13  mov     ebx, 1
0x180029c18  jmp     short loc_180029BB9
0x180029c1a  mov     ecx, 10h; cb
0x180029c1f  call    cs:__imp_CoTaskMemAlloc
0x180029c25  test    rax, rax
0x180029c28  jz      short loc_180029C5F
0x180029c2a  cmp     dword ptr [rsi+40h], 0
0x180029c2e  jz      short loc_180029C3B
0x180029c30  mov     rcx, rax; pv
0x180029c33  call    cs:__imp_CoTaskMemFree
0x180029c39  jmp     short loc_180029C13
0x180029c3b  movups  xmm0, xmmword ptr [rsi+44h]
0x180029c3f  xor     ebx, ebx
0x180029c41  movdqu  xmmword ptr [rax], xmm0
0x180029c45  mov     [r14], rax
0x180029c48  test    rdi, rdi
0x180029c4b  jz      short loc_180029C53
0x180029c4d  mov     dword ptr [rdi], 1
0x180029c53  mov     dword ptr [rsi+40h], 1
0x180029c5a  jmp     loc_180029BB9
0x180029c5f  mov     ebx, 8007000Eh
0x180029c64  jmp     loc_180029BB9
```
