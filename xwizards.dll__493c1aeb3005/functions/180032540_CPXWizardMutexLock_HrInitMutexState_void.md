# CPXWizardMutexLock::HrInitMutexState(void)

- ea: `0x180032540`
- end: `0x1800325dd`
- name: `?HrInitMutexState@CPXWizardMutexLock@@AEAAJXZ`
- size: `157`
- prototype: `__int64 __fastcall(CPXWizardMutexLock *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800323a4`

## callees

- `0x180004370`
- `0x18000ae04`
- `0x180032540`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18003255a`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18003255a`

## pseudocode

```c
__int64 __fastcall CPXWizardMutexLock::HrInitMutexState(LPCWSTR *this)
{
  unsigned int v1; // edi
  const WCHAR *v3; // rax
  PVOID *v4; // rcx
  unsigned int LastErrorHRESULT; // eax

  v1 = *(_DWORD *)this;
  v3 = (const WCHAR *)OpenMutexW(0x1F0001u, 0, this[2]);
  this[1] = v3;
  if ( v3 )
    goto LABEL_5;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    LastErrorHRESULT = GetLastErrorHRESULT();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids, LastErrorHRESULT);
LABEL_5:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x10) != 0 )
    WPP_SF_d(v4[2], 14, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x180032540  mov     [rsp+arg_0], rbx
0x180032545  push    rdi
0x180032546  sub     rsp, 20h
0x18003254a  mov     edi, [rcx]
0x18003254c  mov     rbx, rcx
0x18003254f  mov     r8, [rcx+10h]; lpName
0x180032553  xor     edx, edx; bInheritHandle
0x180032555  mov     ecx, 1F0001h; dwDesiredAccess
0x18003255a  call    cs:__imp_OpenMutexW
0x180032560  mov     [rbx+8], rax
0x180032564  lea     rbx, WPP_GLOBAL_Control
0x18003256b  test    rax, rax
0x18003256e  jnz     short loc_1800325A6
0x180032570  mov     rcx, cs:WPP_GLOBAL_Control
0x180032577  cmp     rcx, rbx
0x18003257a  jz      short loc_1800325D0
0x18003257c  test    byte ptr [rcx+1Ch], 10h
0x180032580  jz      short loc_1800325AD
0x180032582  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180032587  mov     rcx, cs:WPP_GLOBAL_Control
0x18003258e  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x180032595  mov     edx, 0Dh
0x18003259a  mov     r9d, eax
0x18003259d  mov     rcx, [rcx+10h]
0x1800325a1  call    WPP_SF_d
0x1800325a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800325ad  cmp     rcx, rbx
0x1800325b0  jz      short loc_1800325D0
0x1800325b2  test    byte ptr [rcx+1Ch], 10h
0x1800325b6  jz      short loc_1800325D0
0x1800325b8  mov     rcx, [rcx+10h]
0x1800325bc  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x1800325c3  mov     edx, 0Eh
0x1800325c8  mov     r9d, edi
0x1800325cb  call    WPP_SF_d
0x1800325d0  mov     rbx, [rsp+28h+arg_0]
0x1800325d5  mov     eax, edi
0x1800325d7  add     rsp, 20h
0x1800325db  pop     rdi
0x1800325dc  retn
```
