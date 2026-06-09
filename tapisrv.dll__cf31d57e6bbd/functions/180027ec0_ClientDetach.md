# ClientDetach

- ea: `0x180027ec0`
- end: `0x1800280f2`
- name: `ClientDetach`
- size: `562`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180027ec0`
- `0x18002ba70`
- `0x18002efa8`
- `0x18002f06c`
- `0x18003dc84`
- `0x18003e15c`
- `0x18003e3b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002802d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002805b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002807b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002802d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002805b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002807b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180027fc9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180027fc9`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180027f47`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180027f47`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180027f95`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002800f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180027f95`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002800f`
- `RPCRT4!RpcRevertToSelf` at `0x180028097`
- `RPCRT4!RpcRevertToSelf` at `0x180028097`
- `RPCRT4!RpcImpersonateClient` at `0x180027f30`
- `RPCRT4!RpcImpersonateClient` at `0x180027f30`
- `KERNEL32!LeaveCriticalSection` at `0x180028051`
- `KERNEL32!LeaveCriticalSection` at `0x180028051`
- `KERNEL32!EnterCriticalSection` at `0x180027fb2`
- `KERNEL32!EnterCriticalSection` at `0x180027fb2`

## string_xrefs

- `0x180028086`: `RegOpenCurrentUser failed, err=%ld`
- `0x180028066`: `RegCreateKeyEx('\HandoffPri') failed, err=%ld`
- `0x1800280a2`: `ClientDetach: RpcImpersonateClient failed, err=%d`

## pseudocode

```c
__int64 __fastcall ClientDetach(_QWORD *a1)
{
  unsigned int v1; // ebx
  __int64 v3; // rcx
  __int64 result; // rax
  __int64 v5; // rbx
  RPC_STATUS v6; // eax
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  __int64 v9; // rcx
  DWORD dwDisposition; // [rsp+70h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+28h] BYREF
  HKEY v12; // [rsp+80h] [rbp+30h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+38h] BYREF

  v1 = *(_DWORD *)a1;
  TRACELogPrint(524290, "ClientDetach: enter");
  result = ReferenceObject(v3, v1, 1414417475);
  v5 = result;
  if ( result )
  {
    if ( (*(_QWORD *)(result + 8) & 0xFFFFFFFFFFFFFFFEuLL) != 0xFFFFFFFFFFFFFFFEuLL && *(_QWORD *)(result + 8) != -3 )
    {
      hKey = 0;
      phkResult = 0;
      dwDisposition = 0;
      v6 = RpcImpersonateClient(0);
      if ( v6 )
      {
        TRACELogPrint(65538, "ClientDetach: RpcImpersonateClient failed, err=%d", v6);
      }
      else
      {
        v7 = RegOpenCurrentUser(0xF003Fu, &phkResult);
        if ( v7 )
        {
          TRACELogPrint(65538, "RegOpenCurrentUser failed, err=%ld", v7);
        }
        else
        {
          v8 = RegCreateKeyExW(
                 phkResult,
                 L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony\\HandoffPriorities",
                 0,
                 (LPWSTR)&Format,
                 0,
                 2u,
                 0,
                 &hKey,
                 &dwDisposition);
          if ( v8 )
          {
            TRACELogPrint(65538, "RegCreateKeyEx('\\HandoffPri') failed, err=%ld", v8);
          }
          else
          {
            v12 = 0;
            EnterCriticalSection(&gPriorityListCritSec);
            RegDeleteKeyExW(hKey, L"MediaModes", 0, 0);
            if ( !RegCreateKeyExW(hKey, L"MediaModes", 0, (LPWSTR)&Format, 0, 2u, 0, &v12, &dwDisposition) )
            {
              SetMediaModesPriorityList(v12);
              RegCloseKey(v12);
            }
            SetPriorityList(hKey, L"RequestMediaCall", qword_180051968);
            LeaveCriticalSection(&gPriorityListCritSec);
            RegCloseKey(hKey);
          }
          RegCloseKey(phkResult);
        }
        RpcRevertToSelf();
      }
    }
    PCONTEXT_HANDLE_TYPE_rundown(*a1);
    *a1 = 0;
    --dword_1800518BC;
    TRACELogPrint(524290, "ClientDetach: exit");
    return DereferenceObject(v9, *(unsigned int *)(v5 + 248), 1);
  }
  return result;
}

```

## disassembly

```asm
0x180027ec0  push    rbp
0x180027ec2  push    rbx
0x180027ec3  push    rdi
0x180027ec4  mov     rbp, rsp
0x180027ec7  sub     rsp, 50h
0x180027ecb  mov     ebx, [rcx]
0x180027ecd  lea     rdx, aClientdetachEn; "ClientDetach: enter"
0x180027ed4  mov     rdi, rcx
0x180027ed7  mov     ecx, 80002h
0x180027edc  call    TRACELogPrint
0x180027ee1  mov     r8d, 544E4C43h
0x180027ee7  mov     edx, ebx
0x180027ee9  call    ReferenceObject
0x180027eee  mov     rbx, rax
0x180027ef1  test    rax, rax
0x180027ef4  jz      loc_1800280EA
0x180027efa  mov     rcx, [rax+8]
0x180027efe  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180027f02  cmp     rcx, 0FFFFFFFFFFFFFFFEh
0x180027f06  jz      loc_1800280B3
0x180027f0c  cmp     qword ptr [rax+8], 0FFFFFFFFFFFFFFFDh
0x180027f11  jz      loc_1800280B3
0x180027f17  xor     ecx, ecx; BindingHandle
0x180027f19  mov     [rbp+hKey], 0
0x180027f21  mov     [rbp+phkResult], 0
0x180027f29  mov     [rbp+dwDisposition], 0
0x180027f30  call    cs:__imp_RpcImpersonateClient
0x180027f36  test    eax, eax
0x180027f38  jnz     loc_18002809F
0x180027f3e  lea     rdx, [rbp+phkResult]; phkResult
0x180027f42  mov     ecx, 0F003Fh; samDesired
0x180027f47  call    cs:__imp_RegOpenCurrentUser
0x180027f4d  test    eax, eax
0x180027f4f  jnz     loc_180028083
0x180027f55  mov     rcx, [rbp+phkResult]; hKey
0x180027f59  lea     rax, [rbp+dwDisposition]
0x180027f5d  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x180027f62  lea     r9, Format; lpClass
0x180027f69  lea     rax, [rbp+hKey]
0x180027f6d  xor     r8d, r8d; Reserved
0x180027f70  mov     [rsp+50h+var_18], rax; phkResult
0x180027f75  lea     rdx, gszRegKeyHandoffPriorities; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180027f7c  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180027f85  mov     [rsp+50h+samDesired], 2; samDesired
0x180027f8d  mov     [rsp+50h+dwOptions], 0; dwOptions
0x180027f95  call    cs:__imp_RegCreateKeyExW
0x180027f9b  test    eax, eax
0x180027f9d  jnz     loc_180028063
0x180027fa3  lea     rcx, gPriorityListCritSec; lpCriticalSection
0x180027faa  mov     [rbp+arg_10], 0
0x180027fb2  call    cs:__imp_EnterCriticalSection
0x180027fb8  mov     rcx, [rbp+hKey]; hKey
0x180027fbc  lea     rdx, gszRegKeyHandoffPrioritiesMediaModes; "MediaModes"
0x180027fc3  xor     r9d, r9d; Reserved
0x180027fc6  xor     r8d, r8d; samDesired
0x180027fc9  call    cs:__imp_RegDeleteKeyExW
0x180027fcf  mov     rcx, [rbp+hKey]; hKey
0x180027fd3  lea     rax, [rbp+dwDisposition]
0x180027fd7  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x180027fdc  lea     r9, Format; lpClass
0x180027fe3  lea     rax, [rbp+arg_10]
0x180027fe7  xor     r8d, r8d; Reserved
0x180027fea  mov     [rsp+50h+var_18], rax; phkResult
0x180027fef  lea     rdx, gszRegKeyHandoffPrioritiesMediaModes; "MediaModes"
0x180027ff6  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180027fff  mov     [rsp+50h+samDesired], 2; samDesired
0x180028007  mov     [rsp+50h+dwOptions], 0; dwOptions
0x18002800f  call    cs:__imp_RegCreateKeyExW
0x180028015  test    eax, eax
0x180028017  jnz     short loc_180028033
0x180028019  mov     rdx, cs:Src
0x180028020  mov     rcx, [rbp+arg_10]; hKey
0x180028024  call    SetMediaModesPriorityList
0x180028029  mov     rcx, [rbp+arg_10]; hKey
0x18002802d  call    cs:__imp_RegCloseKey
0x180028033  mov     r8, cs:qword_180051968; lpString
0x18002803a  lea     rdx, gszRequestMediaCallW; "RequestMediaCall"
0x180028041  mov     rcx, [rbp+hKey]; hKey
0x180028045  call    SetPriorityList
0x18002804a  lea     rcx, gPriorityListCritSec; lpCriticalSection
0x180028051  call    cs:__imp_LeaveCriticalSection
0x180028057  mov     rcx, [rbp+hKey]; hKey
0x18002805b  call    cs:__imp_RegCloseKey
0x180028061  jmp     short loc_180028077
0x180028063  mov     r8d, eax
0x180028066  lea     rdx, aRegcreatekeyex_0; "RegCreateKeyEx('\\HandoffPri') failed, "...
0x18002806d  mov     ecx, 10002h
0x180028072  call    TRACELogPrint
0x180028077  mov     rcx, [rbp+phkResult]; hKey
0x18002807b  call    cs:__imp_RegCloseKey
0x180028081  jmp     short loc_180028097
0x180028083  mov     r8d, eax
0x180028086  lea     rdx, aRegopencurrent; "RegOpenCurrentUser failed, err=%ld"
0x18002808d  mov     ecx, 10002h
0x180028092  call    TRACELogPrint
0x180028097  call    cs:__imp_RpcRevertToSelf
0x18002809d  jmp     short loc_1800280B3
0x18002809f  mov     r8d, eax
0x1800280a2  lea     rdx, aClientdetachRp; "ClientDetach: RpcImpersonateClient fail"...
0x1800280a9  mov     ecx, 10002h
0x1800280ae  call    TRACELogPrint
0x1800280b3  mov     rcx, [rdi]
0x1800280b6  call    PCONTEXT_HANDLE_TYPE_rundown
0x1800280bb  mov     qword ptr [rdi], 0
0x1800280c2  lea     rdx, aClientdetachEx; "ClientDetach: exit"
0x1800280c9  dec     cs:dword_1800518BC
0x1800280cf  mov     ecx, 80002h
0x1800280d4  call    TRACELogPrint
0x1800280d9  mov     edx, [rbx+0F8h]
0x1800280df  mov     r8d, 1
0x1800280e5  call    DereferenceObject
0x1800280ea  add     rsp, 50h
0x1800280ee  pop     rdi
0x1800280ef  pop     rbx
0x1800280f0  pop     rbp
0x1800280f1  retn
```
