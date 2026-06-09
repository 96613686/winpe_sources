# s_GetProfile(bool,ICachedPrivateProfile * *)

- ea: `0x1800615c8`
- end: `0x1800616fb`
- name: `?s_GetProfile@@YAJ_NPEAPEAUICachedPrivateProfile@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(bool, struct ICachedPrivateProfile **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180061240`
- `0x1800613a0`

## callees

- `0x180030f64`
- `0x1800358c0`
- `0x1800615c8`
- `0x180061704`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061657`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061657`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180061684`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180061684`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180061638`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180061638`

## pseudocode

```c
__int64 __fastcall s_GetProfile(char a1, LPVOID *a2)
{
  HRESULT ProfilePath; // ebx
  HANDLE FileW; // rax
  LPVOID v6; // rcx
  LPVOID ppv; // [rsp+40h] [rbp-238h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-228h] BYREF

  *a2 = 0;
  ProfilePath = s_GetProfilePath(FileName);
  if ( ProfilePath >= 0 )
  {
    if ( a1 )
    {
      FileW = CreateFileW(FileName, 0x40000000u, 0, 0, 2u, 2u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        ProfilePath = ResultFromKnownLastError();
        if ( ProfilePath < 0 )
          return (unsigned int)ProfilePath;
      }
      else
      {
        CloseHandle(FileW);
      }
    }
    ppv = 0;
    ProfilePath = CoCreateInstance(&CLSID_PrivateProfile, 0, 1u, &GUID_b57046bc_32e5_428a_9887_19f712b907bf, &ppv);
    if ( ProfilePath >= 0 )
    {
      ProfilePath = (*(__int64 (__fastcall **)(LPVOID, WCHAR *, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, FileName, 0);
      if ( ProfilePath >= 0 )
      {
        v6 = ppv;
        *a2 = ppv;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 8LL))(v6);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  return (unsigned int)ProfilePath;
}

```

## disassembly

```asm
0x1800615c8  mov     [rsp+arg_0], rbx
0x1800615cd  mov     [rsp+arg_10], rsi
0x1800615d2  push    rdi
0x1800615d3  sub     rsp, 270h
0x1800615da  mov     rax, cs:__security_cookie
0x1800615e1  xor     rax, rsp
0x1800615e4  mov     [rsp+278h+var_18], rax
0x1800615ec  mov     dil, cl
0x1800615ef  mov     qword ptr [rdx], 0
0x1800615f6  lea     rcx, [rsp+278h+FileName]; pszDest
0x1800615fb  mov     rsi, rdx
0x1800615fe  call    ?s_GetProfilePath@@YAJPEAG@Z; s_GetProfilePath(ushort *)
0x180061603  mov     ebx, eax
0x180061605  test    eax, eax
0x180061607  js      loc_1800616D4
0x18006160d  test    dil, dil
0x180061610  jz      short loc_18006165D
0x180061612  mov     eax, 2
0x180061617  mov     [rsp+278h+hTemplateFile], 0; hTemplateFile
0x180061620  mov     [rsp+278h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180061624  lea     rcx, [rsp+278h+FileName]; lpFileName
0x180061629  xor     r9d, r9d; lpSecurityAttributes
0x18006162c  mov     [rsp+278h+dwCreationDisposition], eax; dwCreationDisposition
0x180061630  xor     r8d, r8d; dwShareMode
0x180061633  mov     edx, 40000000h; dwDesiredAccess
0x180061638  call    cs:__imp_CreateFileW
0x18006163e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180061642  jnz     short loc_180061654
0x180061644  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180061649  mov     ebx, eax
0x18006164b  test    eax, eax
0x18006164d  jns     short loc_18006165D
0x18006164f  jmp     loc_1800616D4
0x180061654  mov     rcx, rax; hObject
0x180061657  call    cs:__imp_CloseHandle
0x18006165d  xor     edx, edx; pUnkOuter
0x18006165f  mov     [rsp+278h+ppv], 0
0x180061668  lea     rax, [rsp+278h+ppv]
0x18006166d  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf; riid
0x180061674  mov     qword ptr [rsp+278h+dwCreationDisposition], rax; ppv
0x180061679  lea     rcx, CLSID_PrivateProfile; rclsid
0x180061680  lea     r8d, [rdx+1]; dwClsContext
0x180061684  call    cs:__imp_CoCreateInstance
0x18006168a  mov     ebx, eax
0x18006168c  test    eax, eax
0x18006168e  js      short loc_1800616D4
0x180061690  mov     rcx, [rsp+278h+ppv]
0x180061695  lea     rdx, [rsp+278h+FileName]
0x18006169a  xor     r8d, r8d
0x18006169d  mov     rax, [rcx]
0x1800616a0  mov     rax, [rax+18h]
0x1800616a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800616a9  mov     ebx, eax
0x1800616ab  test    eax, eax
0x1800616ad  js      short loc_1800616C3
0x1800616af  mov     rcx, [rsp+278h+ppv]
0x1800616b4  mov     [rsi], rcx
0x1800616b7  mov     rax, [rcx]
0x1800616ba  mov     rax, [rax+8]
0x1800616be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800616c3  mov     rcx, [rsp+278h+ppv]
0x1800616c8  mov     rax, [rcx]
0x1800616cb  mov     rax, [rax+10h]
0x1800616cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800616d4  mov     eax, ebx
0x1800616d6  mov     rcx, [rsp+278h+var_18]
0x1800616de  xor     rcx, rsp; StackCookie
0x1800616e1  call    __security_check_cookie
0x1800616e6  lea     r11, [rsp+278h+var_8]
0x1800616ee  mov     rbx, [r11+10h]
0x1800616f2  mov     rsi, [r11+20h]
0x1800616f6  mov     rsp, r11
0x1800616f9  pop     rdi
0x1800616fa  retn
```
