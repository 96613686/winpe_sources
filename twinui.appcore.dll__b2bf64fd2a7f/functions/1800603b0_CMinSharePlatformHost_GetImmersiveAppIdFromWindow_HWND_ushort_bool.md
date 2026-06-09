# CMinSharePlatformHost::GetImmersiveAppIdFromWindow(HWND__ *,ushort * *,bool *)

- ea: `0x1800603b0`
- end: `0x18006043e`
- name: `?GetImmersiveAppIdFromWindow@CMinSharePlatformHost@@UEAAJPEAUHWND__@@PEAPEAGPEA_N@Z`
- size: `142`
- prototype: `int(CMinSharePlatformHost *__hidden this, HWND, unsigned __int16 **, bool *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180026ba4`
- `0x1800299c8`
- `0x18005f54c`
- `0x1800603b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800603f0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800603f0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800603cf`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800603cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMinSharePlatformHost::GetImmersiveAppIdFromWindow(
        CMinSharePlatformHost *this,
        HWND a2,
        unsigned __int16 **a3,
        bool *a4)
{
  int ProcessAppId; // edi
  HANDLE v7; // rbx
  unsigned __int16 **v8; // r8
  DWORD dwProcessId; // [rsp+20h] [rbp-38h] BYREF
  HANDLE v11[6]; // [rsp+28h] [rbp-30h] BYREF

  dwProcessId = 0;
  if ( GetWindowThreadProcessId(a2, &dwProcessId) || (ProcessAppId = ResultFromKnownLastError(), ProcessAppId >= 0) )
  {
    v7 = OpenProcess(0x1000u, 0, dwProcessId);
    v11[0] = v7;
    if ( (((unsigned __int64)v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
      || (ProcessAppId = ResultFromKnownLastError(), ProcessAppId >= 0) )
    {
      ProcessAppId = CallerIdentity::GetProcessAppId(v7, a3, v8);
      if ( a4 )
        *a4 = 0;
    }
    CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(v11);
  }
  return (unsigned int)ProcessAppId;
}

```

## disassembly

```asm
0x1800603b0  push    rbx
0x1800603b2  push    rbp
0x1800603b3  push    rsi
0x1800603b4  push    rdi
0x1800603b5  sub     rsp, 38h
0x1800603b9  mov     rsi, r9
0x1800603bc  mov     rbp, r8
0x1800603bf  mov     rcx, rdx; hWnd
0x1800603c2  mov     [rsp+58h+dwProcessId], 0
0x1800603ca  lea     rdx, [rsp+58h+dwProcessId]; lpdwProcessId
0x1800603cf  call    cs:__imp_GetWindowThreadProcessId
0x1800603d5  test    eax, eax
0x1800603d7  jnz     short loc_1800603E4
0x1800603d9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800603de  mov     edi, eax
0x1800603e0  test    eax, eax
0x1800603e2  js      short loc_180060433
0x1800603e4  mov     r8d, [rsp+58h+dwProcessId]; dwProcessId
0x1800603e9  xor     edx, edx; bInheritHandle
0x1800603eb  mov     ecx, 1000h; dwDesiredAccess
0x1800603f0  call    cs:__imp_OpenProcess
0x1800603f6  mov     rbx, rax
0x1800603f9  mov     [rsp+58h+var_30], rax
0x1800603fe  inc     rax
0x180060401  test    rax, 0FFFFFFFFFFFFFFFEh
0x180060407  jnz     short loc_180060414
0x180060409  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006040e  mov     edi, eax
0x180060410  test    eax, eax
0x180060412  js      short loc_180060429
0x180060414  mov     rdx, rbp; void *
0x180060417  mov     rcx, rbx; ProcessHandle
0x18006041a  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x18006041f  mov     edi, eax
0x180060421  test    rsi, rsi
0x180060424  jz      short loc_180060429
0x180060426  mov     byte ptr [rsi], 0
0x180060429  lea     rcx, [rsp+58h+var_30]
0x18006042e  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180060433  mov     eax, edi
0x180060435  add     rsp, 38h
0x180060439  pop     rdi
0x18006043a  pop     rsi
0x18006043b  pop     rbp
0x18006043c  pop     rbx
0x18006043d  retn
```
