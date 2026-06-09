# WctInitClient(ulong,ulong,_WCT_CLIENT_HANDLE *)

- ea: `0x18005eb48`
- end: `0x18005ec86`
- name: `?WctInitClient@@YAKKKPEAU_WCT_CLIENT_HANDLE@@@Z`
- size: `318`
- prototype: `unsigned int __fastcall(DWORD dwThreadId, unsigned int, struct _WCT_CLIENT_HANDLE *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18005d2e0`
- `0x18005e1a4`

## callees

- `0x180004bb4`
- `0x18001fe24`
- `0x18005cd40`
- `0x18005eb48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18005ebce`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18005ebce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ebdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ebdc`
- `ntdll!RtlNtStatusToDosError` at `0x18005ec34`
- `ntdll!RtlNtStatusToDosError` at `0x18005ec34`
- `ntdll!NtQueryInformationThread` at `0x18005ebfe`
- `ntdll!NtQueryInformationThread` at `0x18005ebfe`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005ec1f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005ec1f`

## pseudocode

```c
__int64 __fastcall WctInitClient(DWORD dwThreadId, __int64 a2, struct _WCT_CLIENT_HANDLE *a3)
{
  __int64 v3; // rbx
  unsigned int v5; // ebx
  HANDLE v6; // rax
  DWORD LastError; // eax
  int v8; // eax
  DWORD v9; // r8d
  HANDLE v10; // rax
  __int128 ThreadInformation; // [rsp+30h] [rbp-38h] BYREF
  __int128 dwProcessId; // [rsp+40h] [rbp-28h]
  __int128 v14; // [rsp+50h] [rbp-18h]
  ULONG ReturnLength; // [rsp+78h] [rbp+10h] BYREF

  v3 = dwThreadId;
  ThreadInformation = 0;
  ReturnLength = 0;
  dwProcessId = 0;
  v14 = 0;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4c32fa7a72a13340317baef891270170_Traceguids);
  if ( !(_DWORD)v3 )
  {
    v5 = 87;
LABEL_14:
    WctFreeClient(a3);
    goto LABEL_15;
  }
  *((_QWORD *)a3 + 3) = v3;
  *((_QWORD *)a3 + 2) = 0;
  *((_QWORD *)a3 + 1) = 0;
  v6 = OpenThread(0x48u, 0, v3);
  *(_QWORD *)a3 = v6;
  if ( !v6 )
  {
LABEL_7:
    LastError = GetLastError();
    goto LABEL_13;
  }
  v8 = NtQueryInformationThread(v6, ThreadBasicInformation, &ThreadInformation, 0x30u, &ReturnLength);
  if ( v8 >= 0 && ReturnLength == 48 )
  {
    v9 = dwProcessId;
    *((_QWORD *)a3 + 2) = dwProcessId;
    v10 = OpenProcess(0x450u, 0, v9);
    *((_QWORD *)a3 + 1) = v10;
    if ( v10 )
    {
      v5 = 0;
      goto LABEL_15;
    }
    goto LABEL_7;
  }
  LastError = RtlNtStatusToDosError(v8);
LABEL_13:
  v5 = LastError;
  if ( LastError )
    goto LABEL_14;
LABEL_15:
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_4c32fa7a72a13340317baef891270170_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18005eb48  mov     rax, rsp
0x18005eb4b  mov     [rax+8], rbx
0x18005eb4f  mov     [rax+18h], rbp
0x18005eb53  mov     [rax+10h], edx
0x18005eb56  push    rdi
0x18005eb57  sub     rsp, 60h
0x18005eb5b  xorps   xmm0, xmm0
0x18005eb5e  mov     ebx, ecx
0x18005eb60  movups  xmmword ptr [rax-38h], xmm0
0x18005eb64  mov     rdi, r8
0x18005eb67  mov     dword ptr [rax+10h], 0
0x18005eb6e  movups  xmmword ptr [rax-28h], xmm0
0x18005eb72  movups  xmmword ptr [rax-18h], xmm0
0x18005eb76  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eb7d  lea     rbp, WPP_GLOBAL_Control
0x18005eb84  cmp     rcx, rbp
0x18005eb87  jz      short loc_18005EBA4
0x18005eb89  test    byte ptr [rcx+1Ch], 4
0x18005eb8d  jz      short loc_18005EBA4
0x18005eb8f  mov     rcx, [rcx+10h]
0x18005eb93  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005eb9a  mov     edx, 0Ch
0x18005eb9f  call    WPP_SF_
0x18005eba4  test    ebx, ebx
0x18005eba6  jnz     short loc_18005EBB2
0x18005eba8  mov     ebx, 57h ; 'W'
0x18005ebad  jmp     loc_18005EC40
0x18005ebb2  xor     edx, edx; bInheritHandle
0x18005ebb4  mov     [rdi+18h], rbx
0x18005ebb8  mov     r8d, ebx; dwThreadId
0x18005ebbb  mov     qword ptr [rdi+10h], 0
0x18005ebc3  mov     qword ptr [rdi+8], 0
0x18005ebcb  lea     ecx, [rdx+48h]; dwDesiredAccess
0x18005ebce  call    cs:__imp_OpenThread
0x18005ebd4  mov     [rdi], rax
0x18005ebd7  test    rax, rax
0x18005ebda  jnz     short loc_18005EBE4
0x18005ebdc  call    cs:__imp_GetLastError
0x18005ebe2  jmp     short loc_18005EC3A
0x18005ebe4  lea     rcx, [rsp+68h+arg_8]
0x18005ebe9  mov     r9d, 30h ; '0'; ThreadInformationLength
0x18005ebef  mov     [rsp+68h+ReturnLength], rcx; ReturnLength
0x18005ebf4  lea     r8, [rsp+68h+ThreadInformation]; ThreadInformation
0x18005ebf9  mov     rcx, rax; ThreadHandle
0x18005ebfc  xor     edx, edx; ThreadInformationClass
0x18005ebfe  call    cs:__imp_NtQueryInformationThread
0x18005ec04  test    eax, eax
0x18005ec06  js      short loc_18005EC32
0x18005ec08  cmp     [rsp+68h+arg_8], 30h ; '0'
0x18005ec0d  jnz     short loc_18005EC32
0x18005ec0f  mov     r8, qword ptr [rsp+68h+dwProcessId]; dwProcessId
0x18005ec14  xor     edx, edx; bInheritHandle
0x18005ec16  mov     ecx, 450h; dwDesiredAccess
0x18005ec1b  mov     [rdi+10h], r8
0x18005ec1f  call    cs:__imp_OpenProcess
0x18005ec25  mov     [rdi+8], rax
0x18005ec29  test    rax, rax
0x18005ec2c  jz      short loc_18005EBDC
0x18005ec2e  xor     ebx, ebx
0x18005ec30  jmp     short loc_18005EC48
0x18005ec32  mov     ecx, eax; Status
0x18005ec34  call    cs:__imp_RtlNtStatusToDosError
0x18005ec3a  mov     ebx, eax
0x18005ec3c  test    eax, eax
0x18005ec3e  jz      short loc_18005EC48
0x18005ec40  mov     rcx, rdi; struct _WCT_CLIENT_HANDLE *
0x18005ec43  call    ?WctFreeClient@@YAXPEAU_WCT_CLIENT_HANDLE@@@Z; WctFreeClient(_WCT_CLIENT_HANDLE *)
0x18005ec48  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ec4f  cmp     rcx, rbp
0x18005ec52  jz      short loc_18005EC72
0x18005ec54  test    byte ptr [rcx+1Ch], 4
0x18005ec58  jz      short loc_18005EC72
0x18005ec5a  mov     rcx, [rcx+10h]
0x18005ec5e  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005ec65  mov     edx, 0Dh
0x18005ec6a  mov     r9d, ebx
0x18005ec6d  call    WPP_SF_d
0x18005ec72  lea     r11, [rsp+68h+var_8]
0x18005ec77  mov     eax, ebx
0x18005ec79  mov     rbx, [r11+10h]
0x18005ec7d  mov     rbp, [r11+20h]
0x18005ec81  mov     rsp, r11
0x18005ec84  pop     rdi
0x18005ec85  retn
```
