# GetCurrentUser(Windows::Internal::StateRepository::IUser * *)

- ea: `0x18001c83c`
- end: `0x18001c937`
- name: `?GetCurrentUser@@YAJPEAPEAUIUser@StateRepository@Internal@Windows@@@Z`
- size: `251`
- prototype: `__int64 __fastcall(struct Windows::Internal::StateRepository::IUser **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001c3ec`

## callees

- `0x18001c83c`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c930`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c930`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001c8a7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001c8a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c88a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c88a`

## pseudocode

```c
__int64 __fastcall GetCurrentUser(struct Windows::Internal::StateRepository::IUser **a1)
{
  HRESULT v2; // eax
  int ActivationFactory; // eax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v8; // [rsp+20h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-28h] BYREF
  HSTRING string; // [rsp+40h] [rbp-10h] BYREF

  *a1 = 0;
  v8 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.User", 0x25u, &hstringHeader, &string);
  if ( v2 < 0 )
  {
    RaiseException(v2, 1u, 0, 0);
    JUMPOUT(0x18001C936LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720, &v8);
  v4 = v8;
  v5 = ActivationFactory;
  if ( ActivationFactory < 0
    || (v6 = (*(__int64 (__fastcall **)(__int64, struct Windows::Internal::StateRepository::IUser **))(*(_QWORD *)v8 + 104LL))(
               v8,
               a1),
        v4 = v8,
        v5 = v6,
        v6 < 0) )
  {
    if ( v4 )
    {
      v8 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    return v5;
  }
  else
  {
    if ( v8 )
    {
      v8 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18001c83c  mov     [rsp-8+arg_8], rbx
0x18001c841  mov     [rsp-8+arg_10], rdi
0x18001c846  push    rbp
0x18001c847  mov     rbp, rsp
0x18001c84a  sub     rsp, 50h
0x18001c84e  mov     rax, cs:__security_cookie
0x18001c855  xor     rax, rsp
0x18001c858  mov     [rbp+var_8], rax
0x18001c85c  mov     rdi, rcx
0x18001c85f  mov     qword ptr [rcx], 0
0x18001c866  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x18001c86d  mov     [rbp+var_30], 0
0x18001c875  lea     r9, [rbp+string]; string
0x18001c879  mov     [rbp+string], 0
0x18001c881  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001c885  mov     edx, 25h ; '%'; length
0x18001c88a  call    cs:__imp_WindowsCreateStringReference
0x18001c890  test    eax, eax
0x18001c892  js      loc_18001C924
0x18001c898  mov     rcx, [rbp+string]
0x18001c89c  lea     r8, [rbp+var_30]
0x18001c8a0  lea     rdx, _GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720
0x18001c8a7  call    cs:__imp_RoGetActivationFactory
0x18001c8ad  mov     rcx, [rbp+var_30]
0x18001c8b1  mov     ebx, eax
0x18001c8b3  test    eax, eax
0x18001c8b5  js      short loc_18001C907
0x18001c8b7  mov     rax, [rcx]
0x18001c8ba  mov     rdx, rdi
0x18001c8bd  mov     rax, [rax+68h]
0x18001c8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8c6  mov     rcx, [rbp+var_30]
0x18001c8ca  mov     ebx, eax
0x18001c8cc  test    eax, eax
0x18001c8ce  js      short loc_18001C907
0x18001c8d0  test    rcx, rcx
0x18001c8d3  jz      short loc_18001C8E9
0x18001c8d5  mov     [rbp+var_30], 0
0x18001c8dd  mov     rax, [rcx]
0x18001c8e0  mov     rax, [rax+10h]
0x18001c8e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8e9  xor     eax, eax
0x18001c8eb  mov     rcx, [rbp+var_8]
0x18001c8ef  xor     rcx, rsp; StackCookie
0x18001c8f2  call    __security_check_cookie
0x18001c8f7  mov     rbx, [rsp+50h+arg_8]
0x18001c8fc  mov     rdi, [rsp+50h+arg_10]
0x18001c901  add     rsp, 50h
0x18001c905  pop     rbp
0x18001c906  retn
0x18001c907  test    rcx, rcx
0x18001c90a  jz      short loc_18001C920
0x18001c90c  mov     [rbp+var_30], 0
0x18001c914  mov     rdx, [rcx]
0x18001c917  mov     rax, [rdx+10h]
0x18001c91b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c920  mov     eax, ebx
0x18001c922  jmp     short loc_18001C8EB
0x18001c924  xor     r9d, r9d; lpArguments
0x18001c927  xor     r8d, r8d; nNumberOfArguments
0x18001c92a  mov     ecx, eax; dwExceptionCode
0x18001c92c  lea     edx, [r9+1]; dwExceptionFlags
0x18001c930  call    cs:__imp_RaiseException
```
