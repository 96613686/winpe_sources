# CNTFSSecurity::CreateProgressDialog(ulong)

- ea: `0x1800069b8`
- end: `0x180006b73`
- name: `?CreateProgressDialog@CNTFSSecurity@@IEAAXK@Z`
- size: `443`
- prototype: `void __fastcall(CNTFSSecurity *this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007e00`

## callees

- `0x1800069b8`
- `0x18001d370`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006a4f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006aa9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006a4f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006aa9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800069e6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800069e6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006a20`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006a20`
- `USER32!GetLastActivePopup` at `0x1800069f7`
- `USER32!GetLastActivePopup` at `0x1800069f7`

## pseudocode

```c
void __fastcall CNTFSSecurity::CreateProgressDialog(CNTFSSecurity *this, int a2)
{
  _QWORD *v4; // rsi
  UINT v5; // edx
  int v6; // ebx
  int v7; // ebx
  int (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v9; // [rsp+30h] [rbp-248h] BYREF
  WCHAR Buffer[256]; // [rsp+40h] [rbp-238h] BYREF

  WaitForSingleObject(*((HANDLE *)this + 49), 0xFFFFFFFF);
  v4 = (_QWORD *)((char *)this + 320);
  *((_QWORD *)this + 41) = GetLastActivePopup(*((HWND *)this + 11));
  if ( CoCreateInstance(&CLSID_ProgressDialog, 0, 1u, &IID_IProgressDialog, (LPVOID *)this + 40) >= 0 && *v4 )
  {
    if ( !LoadStringW(g_hInstance, 0x57u, Buffer, 256) )
      Buffer[0] = 0;
    (*(void (__fastcall **)(_QWORD, WCHAR *))(*(_QWORD *)*v4 + 40LL))(*v4, Buffer);
    v5 = 15;
    v6 = a2 - 1;
    if ( v6 )
    {
      v7 = v6 - 3;
      if ( v7 )
      {
        if ( v7 == 4 )
          v5 = 14;
      }
      else
      {
        v5 = 13;
      }
    }
    else
    {
      v5 = 12;
    }
    if ( !LoadStringW(g_hInstance, v5, Buffer, 256) )
      Buffer[0] = 0;
    (*(void (__fastcall **)(_QWORD, __int64, WCHAR *))(*(_QWORD *)*v4 + 80LL))(*v4, 1, Buffer);
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _QWORD))(*(_QWORD *)*v4 + 24LL))(
      *v4,
      *((_QWORD *)this + 41),
      0,
      29,
      0);
    v8 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*v4;
    v9 = 0;
    if ( (**v8)(v8, &IID_IOleWindow, &v9) >= 0 )
    {
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v9 + 24LL))(v9, (char *)this + 328);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    *((_DWORD *)this + 157) = 20;
  }
}

```

## disassembly

```asm
0x1800069b8  push    rbx
0x1800069ba  push    rsi
0x1800069bb  push    rdi
0x1800069bc  push    r14
0x1800069be  sub     rsp, 258h
0x1800069c5  mov     rax, cs:__security_cookie
0x1800069cc  xor     rax, rsp
0x1800069cf  mov     [rsp+278h+var_38], rax
0x1800069d7  mov     ebx, edx
0x1800069d9  mov     rdi, rcx
0x1800069dc  mov     rcx, [rcx+188h]; hHandle
0x1800069e3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800069e6  call    cs:__imp_WaitForSingleObject
0x1800069ec  mov     rcx, [rdi+58h]; hWnd
0x1800069f0  lea     r14, [rdi+148h]
0x1800069f7  call    cs:__imp_GetLastActivePopup
0x1800069fd  xor     edx, edx; pUnkOuter
0x1800069ff  lea     rsi, [rdi+140h]
0x180006a06  lea     r9, IID_IProgressDialog; riid
0x180006a0d  mov     [r14], rax
0x180006a10  lea     rcx, CLSID_ProgressDialog; rclsid
0x180006a17  mov     [rsp+278h+ppv], rsi; ppv
0x180006a1c  lea     r8d, [rdx+1]; dwClsContext
0x180006a20  call    cs:__imp_CoCreateInstance
0x180006a26  test    eax, eax
0x180006a28  js      loc_180006B56
0x180006a2e  cmp     qword ptr [rsi], 0
0x180006a32  jz      loc_180006B56
0x180006a38  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180006a3f  lea     r8, [rsp+278h+Buffer]; lpBuffer
0x180006a44  mov     r9d, 100h; cchBufferMax
0x180006a4a  mov     edx, 57h ; 'W'; uID
0x180006a4f  call    cs:__imp_LoadStringW
0x180006a55  test    eax, eax
0x180006a57  jnz     short loc_180006A5E
0x180006a59  mov     [rsp+278h+Buffer], ax
0x180006a5e  mov     rcx, [rsi]
0x180006a61  lea     rdx, [rsp+278h+Buffer]
0x180006a66  mov     rax, [rcx]
0x180006a69  mov     rax, [rax+28h]
0x180006a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a72  mov     edx, 0Fh
0x180006a77  sub     ebx, 1
0x180006a7a  jz      short loc_180006A92
0x180006a7c  sub     ebx, 3
0x180006a7f  jz      short loc_180006A8B
0x180006a81  cmp     ebx, 4
0x180006a84  jnz     short loc_180006A97
0x180006a86  lea     edx, [rbx+0Ah]
0x180006a89  jmp     short loc_180006A97
0x180006a8b  mov     edx, 0Dh
0x180006a90  jmp     short loc_180006A97
0x180006a92  mov     edx, 0Ch; uID
0x180006a97  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180006a9e  lea     r8, [rsp+278h+Buffer]; lpBuffer
0x180006aa3  mov     r9d, 100h; cchBufferMax
0x180006aa9  call    cs:__imp_LoadStringW
0x180006aaf  test    eax, eax
0x180006ab1  jnz     short loc_180006AB8
0x180006ab3  mov     [rsp+278h+Buffer], ax
0x180006ab8  mov     rcx, [rsi]
0x180006abb  lea     r8, [rsp+278h+Buffer]
0x180006ac0  xor     r9d, r9d
0x180006ac3  mov     [rsp+278h+ppv], 0
0x180006acc  mov     rax, [rcx]
0x180006acf  lea     edx, [r9+1]
0x180006ad3  mov     rax, [rax+50h]
0x180006ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006adc  mov     rcx, [rsi]
0x180006adf  mov     r9d, 1Dh
0x180006ae5  mov     rdx, [r14]
0x180006ae8  xor     r8d, r8d
0x180006aeb  mov     [rsp+278h+ppv], 0
0x180006af4  mov     rax, [rcx]
0x180006af7  mov     rax, [rax+18h]
0x180006afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b00  mov     rcx, [rsi]
0x180006b03  lea     r8, [rsp+278h+var_248]
0x180006b08  mov     [rsp+278h+var_248], 0
0x180006b11  lea     rdx, IID_IOleWindow
0x180006b18  mov     rax, [rcx]
0x180006b1b  mov     rax, [rax]
0x180006b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b23  test    eax, eax
0x180006b25  js      short loc_180006B4C
0x180006b27  mov     rcx, [rsp+278h+var_248]
0x180006b2c  mov     rdx, r14
0x180006b2f  mov     rax, [rcx]
0x180006b32  mov     rax, [rax+18h]
0x180006b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b3b  mov     rcx, [rsp+278h+var_248]
0x180006b40  mov     rax, [rcx]
0x180006b43  mov     rax, [rax+10h]
0x180006b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b4c  mov     dword ptr [rdi+274h], 14h
0x180006b56  mov     rcx, [rsp+278h+var_38]
0x180006b5e  xor     rcx, rsp; StackCookie
0x180006b61  call    __security_check_cookie
0x180006b66  add     rsp, 258h
0x180006b6d  pop     r14
0x180006b6f  pop     rdi
0x180006b70  pop     rsi
0x180006b71  pop     rbx
0x180006b72  retn
```
