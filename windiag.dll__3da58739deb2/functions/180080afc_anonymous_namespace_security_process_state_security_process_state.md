# _anonymous_namespace_::security_process_state::security_process_state

- ea: `0x180080afc`
- end: `0x180080ca7`
- name: `_anonymous_namespace_::security_process_state::security_process_state`
- size: `427`
- prototype: `__int64 __usercall@<rax>(PVOID pv@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180081a00`

## callees

- `0x180004510`
- `0x180005520`
- `0x18003af08`
- `0x180080afc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080c00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080c00`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180080bf4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180080bf4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180080be1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180080be1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080b5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080b7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080ba4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080c15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080c29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080c3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080b5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080b7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080ba4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080c15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080c29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080c3d`

## string_xrefs

- `0x180080c75`: `security_process_state`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall anonymous_namespace_::security_process_state::security_process_state(
        _QWORD *pv,
        void **a2,
        void **a3,
        int a4,
        void **a5,
        __int64 a6)
{
  void *v10; // rbp
  void *v11; // rcx
  void *v12; // rbp
  void *v13; // rcx
  void *v14; // rbp
  void *v15; // rcx
  PTP_WAIT ThreadpoolWait; // rax
  struct _TP_WAIT *v17; // rcx
  DWORD LastError; // eax
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  _BYTE pExceptionObject[1072]; // [rsp+50h] [rbp-478h] BYREF

  *pv = 0;
  v10 = *a2;
  *a2 = 0;
  v11 = (void *)*pv;
  if ( v11 )
  {
    *pv = 0;
    CloseHandle(v11);
  }
  *pv = v10;
  pv[1] = 0;
  v12 = *a3;
  *a3 = 0;
  v13 = (void *)pv[1];
  if ( v13 )
  {
    pv[1] = 0;
    CloseHandle(v13);
  }
  pv[1] = v12;
  *((_DWORD *)pv + 4) = a4;
  pv[3] = 0;
  v14 = *a5;
  *a5 = 0;
  v15 = (void *)pv[3];
  if ( v15 )
  {
    pv[3] = 0;
    CloseHandle(v15);
  }
  pv[3] = v14;
  pv[4] = 0;
  pv[5] = a6;
  pv[6] = 0;
  pv[7] = 0;
  pv[8] = 0;
  pv[9] = 0;
  if ( pv[3] )
  {
    ThreadpoolWait = CreateThreadpoolWait(
                       lambda_bcbf57fb89d09aa043422550589b7216_::_lambda_invoker_cdecl___TP_CALLBACK_INSTANCE___void____TP_WAIT___long_,
                       pv,
                       0);
    v17 = (struct _TP_WAIT *)pv[4];
    pv[4] = ThreadpoolWait;
    if ( v17 )
      CloseThreadpoolWait(v17);
    if ( !pv[4] )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        windiag::system_exception::system_exception(
          (windiag::system_exception *)pExceptionObject,
          LastError,
          0,
          "[%s:%d] failed; ",
          "security_process_state",
          78);
        throw (windiag::system_exception *)pExceptionObject;
      }
    }
  }
  v19 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    CloseHandle(v19);
  }
  *a2 = 0;
  v20 = *a3;
  if ( *a3 )
  {
    *a3 = 0;
    CloseHandle(v20);
  }
  *a3 = 0;
  v21 = *a5;
  if ( *a5 )
  {
    *a5 = 0;
    CloseHandle(v21);
  }
  *a5 = 0;
  return pv;
}

```

## disassembly

```asm
0x180080afc  push    rbx
0x180080afe  push    rbp
0x180080aff  push    rsi
0x180080b00  push    rdi
0x180080b01  push    r12
0x180080b03  push    r14
0x180080b05  push    r15
0x180080b07  sub     rsp, 490h
0x180080b0e  mov     rax, cs:__security_cookie
0x180080b15  xor     rax, rsp
0x180080b18  mov     [rsp+4C8h+var_48], rax
0x180080b20  mov     r15d, r9d
0x180080b23  mov     rdi, r8
0x180080b26  mov     r14, rdx
0x180080b29  mov     rbx, rcx
0x180080b2c  mov     [rsp+4C8h+var_498], rcx
0x180080b31  mov     [rsp+4C8h+var_490], rdx
0x180080b36  mov     [rsp+4C8h+var_488], r8
0x180080b3b  mov     rsi, [rsp+4C8h+arg_20]
0x180080b43  mov     [rsp+4C8h+var_480], rsi
0x180080b48  xor     r12d, r12d
0x180080b4b  mov     [rcx], r12
0x180080b4e  mov     rbp, [rdx]
0x180080b51  mov     [rdx], r12
0x180080b54  mov     rcx, [rcx]; hObject
0x180080b57  test    rcx, rcx
0x180080b5a  jz      short loc_180080B65
0x180080b5c  mov     [rbx], r12
0x180080b5f  call    cs:__imp_CloseHandle
0x180080b65  mov     [rbx], rbp
0x180080b68  mov     [rbx+8], r12
0x180080b6c  mov     rbp, [rdi]
0x180080b6f  mov     [rdi], r12
0x180080b72  mov     rcx, [rbx+8]; hObject
0x180080b76  test    rcx, rcx
0x180080b79  jz      short loc_180080B85
0x180080b7b  mov     [rbx+8], r12
0x180080b7f  call    cs:__imp_CloseHandle
0x180080b85  mov     [rbx+8], rbp
0x180080b89  mov     [rbx+10h], r15d
0x180080b8d  mov     [rbx+18h], r12
0x180080b91  mov     rbp, [rsi]
0x180080b94  mov     [rsi], r12
0x180080b97  mov     rcx, [rbx+18h]; hObject
0x180080b9b  test    rcx, rcx
0x180080b9e  jz      short loc_180080BAA
0x180080ba0  mov     [rbx+18h], r12
0x180080ba4  call    cs:__imp_CloseHandle
0x180080baa  mov     [rbx+18h], rbp
0x180080bae  mov     [rbx+20h], r12
0x180080bb2  mov     rax, [rsp+4C8h+arg_28]
0x180080bba  mov     [rbx+28h], rax
0x180080bbe  mov     [rbx+30h], r12
0x180080bc2  mov     [rbx+38h], r12
0x180080bc6  mov     [rbx+40h], r12
0x180080bca  mov     [rbx+48h], r12
0x180080bce  cmp     [rbx+18h], r12
0x180080bd2  jz      short loc_180080C0A
0x180080bd4  xor     r8d, r8d; pcbe
0x180080bd7  mov     rdx, rbx; pv
0x180080bda  lea     rcx, _lambda_bcbf57fb89d09aa043422550589b7216____lambda_invoker_cdecl___TP_CALLBACK_INSTANCE___void____TP_WAIT___long_; pfnwa
0x180080be1  call    cs:__imp_CreateThreadpoolWait
0x180080be7  mov     rcx, [rbx+20h]; pwa
0x180080beb  mov     [rbx+20h], rax
0x180080bef  test    rcx, rcx
0x180080bf2  jz      short loc_180080BFA
0x180080bf4  call    cs:__imp_CloseThreadpoolWait
0x180080bfa  cmp     [rbx+20h], r12
0x180080bfe  jnz     short loc_180080C0A
0x180080c00  call    cs:__imp_GetLastError
0x180080c06  test    eax, eax
0x180080c08  jnz     short loc_180080C6B
0x180080c0a  mov     rcx, [r14]; hObject
0x180080c0d  test    rcx, rcx
0x180080c10  jz      short loc_180080C1B
0x180080c12  mov     [r14], r12
0x180080c15  call    cs:__imp_CloseHandle
0x180080c1b  mov     [r14], r12
0x180080c1e  mov     rcx, [rdi]; hObject
0x180080c21  test    rcx, rcx
0x180080c24  jz      short loc_180080C2F
0x180080c26  mov     [rdi], r12
0x180080c29  call    cs:__imp_CloseHandle
0x180080c2f  mov     [rdi], r12
0x180080c32  mov     rcx, [rsi]; hObject
0x180080c35  test    rcx, rcx
0x180080c38  jz      short loc_180080C43
0x180080c3a  mov     [rsi], r12
0x180080c3d  call    cs:__imp_CloseHandle
0x180080c43  mov     [rsi], r12
0x180080c46  mov     rax, rbx
0x180080c49  mov     rcx, [rsp+4C8h+var_48]
0x180080c51  xor     rcx, rsp; StackCookie
0x180080c54  call    __security_check_cookie
0x180080c59  add     rsp, 490h
0x180080c60  pop     r15
0x180080c62  pop     r14
0x180080c64  pop     r12
0x180080c66  pop     rdi
0x180080c67  pop     rsi
0x180080c68  pop     rbp
0x180080c69  pop     rbx
0x180080c6a  retn
0x180080c6b  mov     edx, eax; __int64
0x180080c6d  mov     [rsp+4C8h+var_4A0], 4Eh ; 'N'
0x180080c75  lea     rax, aSecurityProces; "security_process_state"
0x180080c7c  mov     [rsp+4C8h+var_4A8], rax
0x180080c81  lea     r9, aSDFailed; "[%s:%d] failed; "
0x180080c88  xor     r8d, r8d; void *
0x180080c8b  lea     rcx, [rsp+4C8h+pExceptionObject]; this
0x180080c90  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x180080c95  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x180080c9c  lea     rcx, [rsp+4C8h+pExceptionObject]; pExceptionObject
0x180080ca1  call    _CxxThrowException_0
```
