# RemoveProviderFromList(TimeProvider *,bool,bool *)

- ea: `0x180010b74`
- end: `0x180010e1e`
- name: `?RemoveProviderFromList@@YAJPEAUTimeProvider@@_NPEA_N@Z`
- size: `682`
- prototype: `__int64 __fastcall(struct TimeProvider *, bool, bool *)`
- caller_count: `12`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180006930`
- `0x180009a80`
- `0x18000ec50`
- `0x18000ee90`
- `0x18000fae0`
- `0x1800103a0`
- `0x18001a9b0`
- `0x180032ff0`
- `0x1800376c0`
- `0x18003891c`
- `0x18004c890`
- `0x18004ceac`

## callees

- `0x18000a7e0`
- `0x180010b74`
- `0x180018138`
- `0x18001d9a0`
- `0x18002f97c`
- `0x18003d270`
- `0x18003dd2c`
- `0x18004c3b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180010bc2`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180010c90`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180010bc2`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180010c90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010d15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010d25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010d34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010d15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010d25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010d34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010cae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010cae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010bda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010bda`

## string_xrefs

- `0x180010d51`: `RemoveProviderFromList: %s\n`
- `0x180010d78`: `RemoveProviderFromList: %s (delayed due to in use)\n`
- `0x180010dc7`: `The time service has been configured to use one or more input providers, however, none of the input providers are still running. THE TIME SERVICE HAS NO SOURCE OF ACCURATE TIME.\n`
- `0x180010df4`: `Provider list after the provider is actually removed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall RemoveProviderFromList(struct TimeProvider *a1, char a2, bool *a3)
{
  __int64 v6; // r14
  __int64 v7; // rcx
  _BYTE *v8; // rdx
  __int64 v9; // rax
  int v10; // ecx
  int v11; // edi
  __int64 v13; // r9
  __int64 v14; // [rsp+30h] [rbp-E8h]
  _BYTE v15[24]; // [rsp+70h] [rbp-A8h] BYREF
  __int64 v16; // [rsp+88h] [rbp-90h]

  memset_0(v15, 0, 0x78u);
  v14 = _set_se_translator(SeTransFunc);
  EnterCriticalSection(&CriticalSection);
  if ( (unsigned __int8)FileLogAllowEntry(64) )
    FileLogAdd(L"RemoveProviderFromList: %s\n", *((_QWORD *)a1 + 1));
  if ( *((_DWORD *)a1 + 18) )
  {
    *((_BYTE *)a1 + 68) = 1;
    if ( (unsigned __int8)FileLogAllowEntry(64) )
      FileLogAdd(L"RemoveProviderFromList: %s (delayed due to in use)\n", *((_QWORD *)a1 + 1));
    if ( a3 )
      *a3 = 1;
    v11 = 0;
  }
  else if ( !*((_BYTE *)a1 + 18) || (v11 = StopProvider(a1), v11 >= 0) )
  {
    v6 = *(_QWORD *)qword_1800A42F0;
    *(_QWORD *)qword_1800A42F0 = v15;
    v7 = v6;
    v16 = v6;
    v8 = v15;
    while ( v6 )
    {
      if ( a1 == (struct TimeProvider *)v6 )
      {
        *((_QWORD *)v8 + 3) = *(_QWORD *)(v6 + 24);
        LocalFree(*(HLOCAL *)v6);
        LocalFree(*(HLOCAL *)(v6 + 8));
        LocalFree((HLOCAL)v6);
        v7 = v16;
        break;
      }
      v8 = (_BYTE *)v6;
      v6 = *(_QWORD *)(v6 + 24);
    }
    *(_QWORD *)qword_1800A42F0 = v7;
    v9 = v16;
    v10 = 0;
    while ( v9 )
    {
      if ( *(_BYTE *)(v9 + 16) )
      {
        if ( !*(_BYTE *)(v9 + 68) )
          ++v10;
      }
      v9 = *(_QWORD *)(v9 + 24);
    }
    if ( v10 )
    {
      byte_1800A45A1 = 1;
    }
    else
    {
      if ( a2 == 1 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(64) )
          FileLogAdd(
            L"The time service has been configured to use one or more input providers, however, none of the input provider"
             "s are still running. THE TIME SERVICE HAS NO SOURCE OF ACCURATE TIME.\n");
        LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_NO_INPUT_PROVIDERS_STARTED, 0, v13);
      }
      byte_1800A45A1 = 0;
    }
    if ( (unsigned __int8)FileLogAllowEntry(121) )
      FileLogTimeProviderList(
        *(struct TimeProvider **)qword_1800A42F0,
        L"Provider list after the provider is actually removed");
    _set_se_translator(v14);
    v11 = 0;
  }
  LeaveCriticalSection(&CriticalSection);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180010b74  mov     [rsp+arg_8], rbx
0x180010b79  mov     [rsp+arg_18], rsi
0x180010b7e  push    rdi
0x180010b7f  push    r14
0x180010b81  push    r15
0x180010b83  sub     rsp, 100h
0x180010b8a  mov     rax, cs:__security_cookie
0x180010b91  xor     rax, rsp
0x180010b94  mov     [rsp+118h+var_28], rax
0x180010b9c  mov     r14, r8
0x180010b9f  mov     r15b, dl
0x180010ba2  mov     rsi, rcx
0x180010ba5  xor     ebx, ebx
0x180010ba7  mov     [rsp+118h+var_F8], bl
0x180010bab  xor     edx, edx; Val
0x180010bad  lea     r8d, [rbx+78h]; Size
0x180010bb1  lea     rcx, [rsp+118h+var_A8]; void *
0x180010bb6  call    memset_0
0x180010bbb  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x180010bc2  call    cs:__imp__set_se_translator
0x180010bc9  nop     dword ptr [rax+rax+00h]
0x180010bce  mov     [rsp+118h+var_E8], rax
0x180010bd3  lea     rcx, CriticalSection; lpCriticalSection
0x180010bda  call    cs:__imp_EnterCriticalSection
0x180010be1  nop     dword ptr [rax+rax+00h]
0x180010be6  mov     edi, ebx
0x180010be8  mov     [rsp+118h+var_F4], ebx
0x180010bec  mov     [rsp+118h+var_F8], 1
0x180010bf1  lea     ecx, [rbx+40h]
0x180010bf4  call    FileLogAllowEntry
0x180010bf9  test    al, al
0x180010bfb  jnz     loc_180010D4D
0x180010c01  cmp     [rsi+48h], ebx
0x180010c04  jnz     loc_180010D62
0x180010c0a  cmp     [rsi+12h], bl
0x180010c0d  jnz     loc_180010D98
0x180010c13  mov     rax, cs:qword_1800A42F0
0x180010c1a  mov     r14, [rax]
0x180010c1d  lea     rcx, [rsp+118h+var_A8]
0x180010c22  mov     [rax], rcx
0x180010c25  mov     rcx, r14
0x180010c28  mov     [rsp+118h+var_90], rcx
0x180010c30  lea     rdx, [rsp+118h+var_A8]
0x180010c35  test    r14, r14
0x180010c38  jnz     loc_180010CFA
0x180010c3e  mov     rax, cs:qword_1800A42F0
0x180010c45  mov     [rax], rcx
0x180010c48  mov     rax, [rsp+118h+var_90]
0x180010c50  mov     ecx, ebx
0x180010c52  mov     [rsp+118h+var_F0], ebx
0x180010c56  test    rax, rax
0x180010c59  jz      short loc_180010C6A
0x180010c5b  cmp     [rax+10h], bl
0x180010c5e  jnz     loc_180010CE6
0x180010c64  mov     rax, [rax+18h]
0x180010c68  jmp     short loc_180010C56
0x180010c6a  test    ecx, ecx
0x180010c6c  jz      loc_180010DB3
0x180010c72  mov     cs:byte_1800A45A1, 1
0x180010c79  mov     ecx, 79h ; 'y'
0x180010c7e  call    FileLogAllowEntry
0x180010c83  test    al, al
0x180010c85  jnz     loc_180010DF4
0x180010c8b  mov     rcx, [rsp+118h+var_E8]
0x180010c90  call    cs:__imp__set_se_translator
0x180010c97  nop     dword ptr [rax+rax+00h]
0x180010c9c  test    edi, edi
0x180010c9e  cmovns  edi, ebx
0x180010ca1  cmp     [rsp+118h+var_F8], bl
0x180010ca5  jz      short loc_180010CBA
0x180010ca7  lea     rcx, CriticalSection; lpCriticalSection
0x180010cae  call    cs:__imp_LeaveCriticalSection
0x180010cb5  nop     dword ptr [rax+rax+00h]
0x180010cba  mov     eax, edi
0x180010cbc  mov     rcx, [rsp+118h+var_28]
0x180010cc4  xor     rcx, rsp; StackCookie
0x180010cc7  call    __security_check_cookie
0x180010ccc  lea     r11, [rsp+118h+var_18]
0x180010cd4  mov     rbx, [r11+28h]
0x180010cd8  mov     rsi, [r11+38h]
0x180010cdc  mov     rsp, r11
0x180010cdf  pop     r15
0x180010ce1  pop     r14
0x180010ce3  pop     rdi
0x180010ce4  retn
0x180010ce6  cmp     [rax+44h], bl
0x180010ce9  jnz     loc_180010C64
0x180010cef  inc     ecx
0x180010cf1  mov     [rsp+118h+var_F0], ecx
0x180010cf5  jmp     loc_180010C64
0x180010cfa  mov     rax, [r14+18h]
0x180010cfe  cmp     rsi, r14
0x180010d01  jz      short loc_180010D0E
0x180010d03  mov     rdx, r14
0x180010d06  mov     r14, rax
0x180010d09  jmp     loc_180010C35
0x180010d0e  mov     [rdx+18h], rax
0x180010d12  mov     rcx, [r14]; hMem
0x180010d15  call    cs:__imp_LocalFree
0x180010d1c  nop     dword ptr [rax+rax+00h]
0x180010d21  mov     rcx, [r14+8]; hMem
0x180010d25  call    cs:__imp_LocalFree
0x180010d2c  nop     dword ptr [rax+rax+00h]
0x180010d31  mov     rcx, r14; hMem
0x180010d34  call    cs:__imp_LocalFree
0x180010d3b  nop     dword ptr [rax+rax+00h]
0x180010d40  mov     rcx, [rsp+118h+var_90]
0x180010d48  jmp     loc_180010C3E
0x180010d4d  mov     rdx, [rsi+8]
0x180010d51  lea     rcx, aRemoveprovider; "RemoveProviderFromList: %s\n"
0x180010d58  call    FileLogAdd
0x180010d5d  jmp     loc_180010C01
0x180010d62  mov     byte ptr [rsi+44h], 1
0x180010d66  mov     ecx, 40h ; '@'
0x180010d6b  call    FileLogAllowEntry
0x180010d70  test    al, al
0x180010d72  jz      short loc_180010D84
0x180010d74  mov     rdx, [rsi+8]
0x180010d78  lea     rcx, aRemoveprovider_0; "RemoveProviderFromList: %s (delayed due"...
0x180010d7f  call    FileLogAdd
0x180010d84  test    r14, r14
0x180010d87  jz      short loc_180010D8D
0x180010d89  mov     byte ptr [r14], 1
0x180010d8d  mov     edi, ebx
0x180010d8f  mov     [rsp+118h+var_F4], ebx
0x180010d93  jmp     loc_180010CA7
0x180010d98  mov     rcx, rsi; struct TimeProvider *
0x180010d9b  call    ?StopProvider@@YAJPEAUTimeProvider@@@Z; StopProvider(TimeProvider *)
0x180010da0  mov     edi, eax
0x180010da2  mov     [rsp+118h+var_F4], eax
0x180010da6  test    eax, eax
0x180010da8  jns     loc_180010C13
0x180010dae  jmp     loc_180010CA7
0x180010db3  cmp     r15b, 1
0x180010db7  jnz     short loc_180010DE9
0x180010db9  mov     ecx, 40h ; '@'
0x180010dbe  call    FileLogAllowEntry
0x180010dc3  test    al, al
0x180010dc5  jz      short loc_180010DD3
0x180010dc7  lea     rcx, aTheTimeService; "The time service has been configured to"...
0x180010dce  call    FileLogAdd
0x180010dd3  xor     r8d, r8d
0x180010dd6  lea     rdx, W32TIME_EVENT_NO_INPUT_PROVIDERS_STARTED
0x180010ddd  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x180010de4  call    LogEvent
0x180010de9  mov     cs:byte_1800A45A1, bl
0x180010def  jmp     loc_180010C79
0x180010df4  lea     rdx, aProviderListAf; "Provider list after the provider is act"...
0x180010dfb  mov     rcx, cs:qword_1800A42F0
0x180010e02  mov     rcx, [rcx]; struct TimeProvider *
0x180010e05  call    ?FileLogTimeProviderList@@YAXPEAUTimeProvider@@PEBG@Z; FileLogTimeProviderList(TimeProvider *,ushort const *)
0x180010e0a  jmp     loc_180010C8B
0x180010e0f  jmp     short loc_180010E13
0x180010e11  jmp     short $+2
0x180010e13  xor     ebx, ebx
0x180010e15  mov     edi, [rsp+118h+var_F4]
0x180010e19  jmp     loc_180010C8B
```
