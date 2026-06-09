# CPXWizardMutexLock::HrInitMutexState(void)

- ea: `0x180011e28`
- end: `0x180011ec5`
- name: `?HrInitMutexState@CPXWizardMutexLock@@AEAAJXZ`
- size: `157`
- prototype: `__int64 __fastcall(CPXWizardMutexLock *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011c8c`

## callees

- `0x180003b90`
- `0x180007820`
- `0x180011e28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180011e42`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180011e42`

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
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids, LastErrorHRESULT);
LABEL_5:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x10) != 0 )
    WPP_SF_D(v4[2], 14, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x180011e28  mov     [rsp+arg_0], rbx
0x180011e2d  push    rdi
0x180011e2e  sub     rsp, 20h
0x180011e32  mov     edi, [rcx]
0x180011e34  mov     rbx, rcx
0x180011e37  mov     r8, [rcx+10h]; lpName
0x180011e3b  xor     edx, edx; bInheritHandle
0x180011e3d  mov     ecx, 1F0001h; dwDesiredAccess
0x180011e42  call    cs:__imp_OpenMutexW
0x180011e48  mov     [rbx+8], rax
0x180011e4c  lea     rbx, WPP_GLOBAL_Control
0x180011e53  test    rax, rax
0x180011e56  jnz     short loc_180011E8E
0x180011e58  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e5f  cmp     rcx, rbx
0x180011e62  jz      short loc_180011EB8
0x180011e64  test    byte ptr [rcx+1Ch], 10h
0x180011e68  jz      short loc_180011E95
0x180011e6a  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180011e6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e76  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x180011e7d  mov     edx, 0Dh
0x180011e82  mov     r9d, eax
0x180011e85  mov     rcx, [rcx+10h]
0x180011e89  call    WPP_SF_D
0x180011e8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e95  cmp     rcx, rbx
0x180011e98  jz      short loc_180011EB8
0x180011e9a  test    byte ptr [rcx+1Ch], 10h
0x180011e9e  jz      short loc_180011EB8
0x180011ea0  mov     rcx, [rcx+10h]
0x180011ea4  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x180011eab  mov     edx, 0Eh
0x180011eb0  mov     r9d, edi
0x180011eb3  call    WPP_SF_D
0x180011eb8  mov     rbx, [rsp+28h+arg_0]
0x180011ebd  mov     eax, edi
0x180011ebf  add     rsp, 20h
0x180011ec3  pop     rdi
0x180011ec4  retn
```
