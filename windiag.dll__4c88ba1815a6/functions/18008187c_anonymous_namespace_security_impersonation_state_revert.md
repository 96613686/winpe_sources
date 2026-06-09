# _anonymous_namespace_::security_impersonation_state::revert

- ea: `0x18008187c`
- end: `0x180081948`
- name: `_anonymous_namespace_::security_impersonation_state::revert`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180083340`

## callees

- `0x180004510`
- `0x180005520`
- `0x18003af08`
- `0x18008187c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800818bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800818bb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800818ac`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800818ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800818da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800818da`

## pseudocode

```c
void __fastcall anonymous_namespace_::security_impersonation_state::revert(__int64 a1, char a2)
{
  DWORD LastError; // eax
  HANDLE v5; // rcx
  _BYTE pExceptionObject[1072]; // [rsp+30h] [rbp-448h] BYREF

  if ( *(_BYTE *)(a1 + 8) )
  {
    if ( !SetThreadToken(0, *(HANDLE *)a1) )
    {
      if ( a2 )
      {
        LastError = GetLastError();
        if ( LastError )
        {
          windiag::system_exception::system_exception(
            (windiag::system_exception *)pExceptionObject,
            LastError,
            0,
            "[%s:%d] failed; ",
            "revert",
            50);
          throw (windiag::system_exception *)pExceptionObject;
        }
      }
    }
    if ( *(_BYTE *)(a1 + 8) )
    {
      v5 = *(HANDLE *)a1;
      if ( *(_QWORD *)a1 )
      {
        *(_QWORD *)a1 = 0;
        CloseHandle(v5);
      }
      *(_QWORD *)a1 = 0;
      *(_BYTE *)(a1 + 8) = 0;
    }
  }
}

```

## disassembly

```asm
0x18008187c  mov     [rsp+arg_8], rbx
0x180081881  push    rdi
0x180081882  sub     rsp, 470h
0x180081889  mov     rax, cs:__security_cookie
0x180081890  xor     rax, rsp
0x180081893  mov     [rsp+478h+var_18], rax
0x18008189b  cmp     byte ptr [rcx+8], 0
0x18008189f  mov     dil, dl
0x1800818a2  mov     rbx, rcx
0x1800818a5  jz      short loc_1800818EB
0x1800818a7  mov     rdx, [rcx]; Token
0x1800818aa  xor     ecx, ecx; Thread
0x1800818ac  call    cs:__imp_SetThreadToken
0x1800818b2  test    eax, eax
0x1800818b4  jnz     short loc_1800818C5
0x1800818b6  test    dil, dil
0x1800818b9  jz      short loc_1800818C5
0x1800818bb  call    cs:__imp_GetLastError
0x1800818c1  test    eax, eax
0x1800818c3  jnz     short loc_18008190C
0x1800818c5  cmp     byte ptr [rbx+8], 0
0x1800818c9  jz      short loc_1800818EB
0x1800818cb  mov     rcx, [rbx]; hObject
0x1800818ce  test    rcx, rcx
0x1800818d1  jz      short loc_1800818E0
0x1800818d3  mov     qword ptr [rbx], 0
0x1800818da  call    cs:__imp_CloseHandle
0x1800818e0  mov     qword ptr [rbx], 0
0x1800818e7  mov     byte ptr [rbx+8], 0
0x1800818eb  mov     rcx, [rsp+478h+var_18]
0x1800818f3  xor     rcx, rsp; StackCookie
0x1800818f6  call    __security_check_cookie
0x1800818fb  mov     rbx, [rsp+478h+arg_8]
0x180081903  add     rsp, 470h
0x18008190a  pop     rdi
0x18008190b  retn
0x18008190c  mov     edx, eax; __int64
0x18008190e  lea     r9, aSDFailed; "[%s:%d] failed; "
0x180081915  lea     rax, aRevert; "revert"
0x18008191c  mov     [rsp+478h+var_450], 32h ; '2'
0x180081924  xor     r8d, r8d; void *
0x180081927  mov     [rsp+478h+var_458], rax
0x18008192c  lea     rcx, [rsp+478h+pExceptionObject]; this
0x180081931  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x180081936  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18008193d  lea     rcx, [rsp+478h+pExceptionObject]; pExceptionObject
0x180081942  call    _CxxThrowException_0
```
