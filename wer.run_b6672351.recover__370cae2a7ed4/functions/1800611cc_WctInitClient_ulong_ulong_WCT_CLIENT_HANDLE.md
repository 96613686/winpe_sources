# WctInitClient(ulong,ulong,_WCT_CLIENT_HANDLE *)

- ea: `0x1800611cc`
- end: `0x180061329`
- name: `?WctInitClient@@YAKKKPEAU_WCT_CLIENT_HANDLE@@@Z`
- size: `349`
- prototype: `unsigned int __fastcall(DWORD dwThreadId, unsigned int, struct _WCT_CLIENT_HANDLE *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18005f878`
- `0x1800607d0`

## callees

- `0x180004c64`
- `0x180020680`
- `0x18005f288`
- `0x1800611cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180061252`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180061252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061266`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061266`
- `ntdll!RtlNtStatusToDosError` at `0x1800612d0`
- `ntdll!RtlNtStatusToDosError` at `0x1800612d0`
- `ntdll!NtQueryInformationThread` at `0x18006128e`
- `ntdll!NtQueryInformationThread` at `0x18006128e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800612b5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800612b5`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x1800611cc  mov     rax, rsp
0x1800611cf  mov     [rax+8], rbx
0x1800611d3  mov     [rax+18h], rbp
0x1800611d7  mov     [rax+10h], edx
0x1800611da  push    rdi
0x1800611db  sub     rsp, 60h
0x1800611df  xorps   xmm0, xmm0
0x1800611e2  mov     ebx, ecx
0x1800611e4  movups  xmmword ptr [rax-38h], xmm0
0x1800611e8  mov     rdi, r8
0x1800611eb  mov     dword ptr [rax+10h], 0
0x1800611f2  movups  xmmword ptr [rax-28h], xmm0
0x1800611f6  movups  xmmword ptr [rax-18h], xmm0
0x1800611fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180061201  lea     rbp, WPP_GLOBAL_Control
0x180061208  cmp     rcx, rbp
0x18006120b  jz      short loc_180061228
0x18006120d  test    byte ptr [rcx+1Ch], 4
0x180061211  jz      short loc_180061228
0x180061213  mov     rcx, [rcx+10h]
0x180061217  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18006121e  mov     edx, 0Ch
0x180061223  call    WPP_SF_
0x180061228  test    ebx, ebx
0x18006122a  jnz     short loc_180061236
0x18006122c  mov     ebx, 57h ; 'W'
0x180061231  jmp     loc_1800612E2
0x180061236  xor     edx, edx; bInheritHandle
0x180061238  mov     [rdi+18h], rbx
0x18006123c  mov     r8d, ebx; dwThreadId
0x18006123f  mov     qword ptr [rdi+10h], 0
0x180061247  mov     qword ptr [rdi+8], 0
0x18006124f  lea     ecx, [rdx+48h]; dwDesiredAccess
0x180061252  call    cs:__imp_OpenThread
0x180061259  nop     dword ptr [rax+rax+00h]
0x18006125e  mov     [rdi], rax
0x180061261  test    rax, rax
0x180061264  jnz     short loc_180061274
0x180061266  call    cs:__imp_GetLastError
0x18006126d  nop     dword ptr [rax+rax+00h]
0x180061272  jmp     short loc_1800612DC
0x180061274  lea     rcx, [rsp+68h+arg_8]
0x180061279  mov     r9d, 30h ; '0'; ThreadInformationLength
0x18006127f  mov     [rsp+68h+ReturnLength], rcx; ReturnLength
0x180061284  lea     r8, [rsp+68h+ThreadInformation]; ThreadInformation
0x180061289  mov     rcx, rax; ThreadHandle
0x18006128c  xor     edx, edx; ThreadInformationClass
0x18006128e  call    cs:__imp_NtQueryInformationThread
0x180061295  nop     dword ptr [rax+rax+00h]
0x18006129a  test    eax, eax
0x18006129c  js      short loc_1800612CE
0x18006129e  cmp     [rsp+68h+arg_8], 30h ; '0'
0x1800612a3  jnz     short loc_1800612CE
0x1800612a5  mov     r8, qword ptr [rsp+68h+dwProcessId]; dwProcessId
0x1800612aa  xor     edx, edx; bInheritHandle
0x1800612ac  mov     ecx, 450h; dwDesiredAccess
0x1800612b1  mov     [rdi+10h], r8
0x1800612b5  call    cs:__imp_OpenProcess
0x1800612bc  nop     dword ptr [rax+rax+00h]
0x1800612c1  mov     [rdi+8], rax
0x1800612c5  test    rax, rax
0x1800612c8  jz      short loc_180061266
0x1800612ca  xor     ebx, ebx
0x1800612cc  jmp     short loc_1800612EA
0x1800612ce  mov     ecx, eax; Status
0x1800612d0  call    cs:__imp_RtlNtStatusToDosError
0x1800612d7  nop     dword ptr [rax+rax+00h]
0x1800612dc  mov     ebx, eax
0x1800612de  test    eax, eax
0x1800612e0  jz      short loc_1800612EA
0x1800612e2  mov     rcx, rdi; struct _WCT_CLIENT_HANDLE *
0x1800612e5  call    ?WctFreeClient@@YAXPEAU_WCT_CLIENT_HANDLE@@@Z; WctFreeClient(_WCT_CLIENT_HANDLE *)
0x1800612ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800612f1  cmp     rcx, rbp
0x1800612f4  jz      short loc_180061314
0x1800612f6  test    byte ptr [rcx+1Ch], 4
0x1800612fa  jz      short loc_180061314
0x1800612fc  mov     rcx, [rcx+10h]
0x180061300  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x180061307  mov     edx, 0Dh
0x18006130c  mov     r9d, ebx
0x18006130f  call    WPP_SF_d
0x180061314  lea     r11, [rsp+68h+var_8]
0x180061319  mov     eax, ebx
0x18006131b  mov     rbx, [r11+10h]
0x18006131f  mov     rbp, [r11+20h]
0x180061323  mov     rsp, r11
0x180061326  pop     rdi
0x180061327  retn
```
