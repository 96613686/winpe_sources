# LoadUserProfileA

- ea: `0x1800084f0`
- end: `0x180008680`
- name: `LoadUserProfileA`
- size: `400`
- prototype: `BOOL __stdcall(HANDLE hToken, LPPROFILEINFOA lpProfileInfo)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800046ac`
- `0x1800084f0`
- `0x180008688`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800085f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000860a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800085f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000860a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800085e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000862f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008640`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008651`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000866f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800085e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000862f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008640`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008651`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000866f`

## pseudocode

```c
BOOL __stdcall LoadUserProfileA(HANDLE hToken, LPPROFILEINFOA lpProfileInfo)
{
  const CHAR *lpUserName; // rcx
  WCHAR *v5; // rax
  const CHAR *lpProfilePath; // rcx
  WCHAR *v7; // rax
  const CHAR *lpDefaultPath; // rcx
  WCHAR *v9; // rax
  const CHAR *lpServerName; // rcx
  int v11; // eax
  BOOL v12; // edi
  BOOL result; // eax
  struct _PROFILEINFOW hMem; // [rsp+20h] [rbp-40h] BYREF

  if ( lpProfileInfo && lpProfileInfo->dwSize == 56 )
  {
    lpUserName = lpProfileInfo->lpUserName;
    memset(&hMem, 0, sizeof(hMem));
    hMem.dwFlags = lpProfileInfo->dwFlags;
    hMem.dwSize = 56;
    v5 = ProduceWFromA(lpUserName);
    lpProfilePath = lpProfileInfo->lpProfilePath;
    hMem.lpUserName = v5;
    v7 = ProduceWFromA(lpProfilePath);
    lpDefaultPath = lpProfileInfo->lpDefaultPath;
    hMem.lpProfilePath = v7;
    v9 = ProduceWFromA(lpDefaultPath);
    lpServerName = lpProfileInfo->lpServerName;
    hMem.lpDefaultPath = v9;
    hMem.lpServerName = ProduceWFromA(lpServerName);
    if ( (hMem.dwFlags & 2) != 0 )
      hMem.lpPolicyPath = ProduceWFromA(lpProfileInfo->lpPolicyPath);
    v11 = LoadUserProfileInternal(hToken, &hMem);
    if ( v11 < 0 )
    {
      SetLastError((unsigned __int16)v11);
      v12 = 0;
    }
    else
    {
      v12 = 1;
    }
    if ( hMem.lpUserName )
      LocalFree(hMem.lpUserName);
    if ( hMem.lpProfilePath )
      LocalFree(hMem.lpProfilePath);
    if ( hMem.lpDefaultPath )
      LocalFree(hMem.lpDefaultPath);
    if ( hMem.lpServerName )
      LocalFree(hMem.lpServerName);
    if ( (hMem.dwFlags & 2) != 0 )
    {
      if ( hMem.lpPolicyPath )
        LocalFree(hMem.lpPolicyPath);
    }
    result = v12;
    lpProfileInfo->hProfile = hMem.hProfile;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800084f0  mov     [rsp-8+arg_0], rbx
0x1800084f5  mov     [rsp-8+arg_8], rdi
0x1800084fa  push    rbp
0x1800084fb  mov     rbp, rsp
0x1800084fe  sub     rsp, 60h
0x180008502  mov     rbx, rdx
0x180008505  mov     rdi, rcx
0x180008508  test    rdx, rdx
0x18000850b  jz      loc_1800085F2
0x180008511  cmp     dword ptr [rdx], 38h ; '8'
0x180008514  jnz     loc_1800085F2
0x18000851a  mov     rcx, [rdx+8]; lpMultiByteStr
0x18000851e  xorps   xmm0, xmm0
0x180008521  xor     eax, eax
0x180008523  movups  xmmword ptr [rbp+hMem], xmm0
0x180008527  mov     [rbp+var_10], rax
0x18000852b  mov     eax, [rdx+4]
0x18000852e  mov     dword ptr [rbp+hMem+4], eax
0x180008531  movups  xmmword ptr [rbp+var_30], xmm0
0x180008535  mov     dword ptr [rbp+hMem], 38h ; '8'
0x18000853c  movups  xmmword ptr [rbp+var_20], xmm0
0x180008540  call    ?ProduceWFromA@@YAPEAGPEBD@Z; ProduceWFromA(char const *)
0x180008545  mov     rcx, [rbx+10h]; lpMultiByteStr
0x180008549  mov     [rbp+hMem+8], rax
0x18000854d  call    ?ProduceWFromA@@YAPEAGPEBD@Z; ProduceWFromA(char const *)
0x180008552  mov     rcx, [rbx+18h]; lpMultiByteStr
0x180008556  mov     [rbp+var_30], rax
0x18000855a  call    ?ProduceWFromA@@YAPEAGPEBD@Z; ProduceWFromA(char const *)
0x18000855f  mov     rcx, [rbx+20h]; lpMultiByteStr
0x180008563  mov     [rbp+var_30+8], rax
0x180008567  call    ?ProduceWFromA@@YAPEAGPEBD@Z; ProduceWFromA(char const *)
0x18000856c  test    byte ptr [rbp+hMem+4], 2
0x180008570  mov     [rbp+var_20], rax
0x180008574  jnz     loc_18000861D
0x18000857a  lea     rdx, [rbp+hMem]; struct _PROFILEINFOW *
0x18000857e  mov     rcx, rdi; TokenHandle
0x180008581  call    ?LoadUserProfileInternal@@YAJPEAXPEAU_PROFILEINFOW@@@Z; LoadUserProfileInternal(void *,_PROFILEINFOW *)
0x180008586  test    eax, eax
0x180008588  js      short loc_180008607
0x18000858a  mov     edi, 1
0x18000858f  mov     rcx, [rbp+hMem+8]; hMem
0x180008593  test    rcx, rcx
0x180008596  jnz     short loc_1800085E4
0x180008598  mov     rcx, [rbp+var_30]; hMem
0x18000859c  test    rcx, rcx
0x18000859f  jnz     loc_18000862F
0x1800085a5  mov     rcx, [rbp+var_30+8]; hMem
0x1800085a9  test    rcx, rcx
0x1800085ac  jnz     loc_180008640
0x1800085b2  mov     rcx, [rbp+var_20]; hMem
0x1800085b6  test    rcx, rcx
0x1800085b9  jnz     loc_180008651
0x1800085bf  test    byte ptr [rbp+hMem+4], 2
0x1800085c3  jnz     loc_180008662
0x1800085c9  mov     rcx, [rbp+var_10]
0x1800085cd  mov     eax, edi
0x1800085cf  mov     [rbx+30h], rcx
0x1800085d3  mov     rbx, [rsp+60h+arg_0]
0x1800085d8  mov     rdi, [rsp+60h+arg_8]
0x1800085dd  add     rsp, 60h
0x1800085e1  pop     rbp
0x1800085e2  retn
0x1800085e4  call    cs:__imp_LocalFree
0x1800085eb  nop     dword ptr [rax+rax+00h]
0x1800085f0  jmp     short loc_180008598
0x1800085f2  mov     ecx, 57h ; 'W'; dwErrCode
0x1800085f7  call    cs:__imp_SetLastError
0x1800085fe  nop     dword ptr [rax+rax+00h]
0x180008603  xor     eax, eax
0x180008605  jmp     short loc_1800085D3
0x180008607  movzx   ecx, ax; dwErrCode
0x18000860a  call    cs:__imp_SetLastError
0x180008611  nop     dword ptr [rax+rax+00h]
0x180008616  xor     edi, edi
0x180008618  jmp     loc_18000858F
0x18000861d  mov     rcx, [rbx+28h]; lpMultiByteStr
0x180008621  call    ?ProduceWFromA@@YAPEAGPEBD@Z; ProduceWFromA(char const *)
0x180008626  mov     [rbp+var_20+8], rax
0x18000862a  jmp     loc_18000857A
0x18000862f  call    cs:__imp_LocalFree
0x180008636  nop     dword ptr [rax+rax+00h]
0x18000863b  jmp     loc_1800085A5
0x180008640  call    cs:__imp_LocalFree
0x180008647  nop     dword ptr [rax+rax+00h]
0x18000864c  jmp     loc_1800085B2
0x180008651  call    cs:__imp_LocalFree
0x180008658  nop     dword ptr [rax+rax+00h]
0x18000865d  jmp     loc_1800085BF
0x180008662  mov     rcx, [rbp+var_20+8]; hMem
0x180008666  test    rcx, rcx
0x180008669  jz      loc_1800085C9
0x18000866f  call    cs:__imp_LocalFree
0x180008676  nop     dword ptr [rax+rax+00h]
0x18000867b  jmp     loc_1800085C9
```
