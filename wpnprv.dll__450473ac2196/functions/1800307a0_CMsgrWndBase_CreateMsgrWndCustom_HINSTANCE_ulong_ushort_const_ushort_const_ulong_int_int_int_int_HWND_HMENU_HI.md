# CMsgrWndBase::CreateMsgrWndCustom(HINSTANCE__ *,ulong,ushort const *,ushort const *,ulong,int,int,int,int,HWND__ *,HMENU__ *,HICON__ *,HICON__ *,ulong)

- ea: `0x1800307a0`
- end: `0x180030ba8`
- name: `?CreateMsgrWndCustom@CMsgrWndBase@@UEAAJPEAUHINSTANCE__@@KPEBG1KHHHHPEAUHWND__@@PEAUHMENU__@@PEAUHICON__@@4K@Z`
- size: `1032`
- prototype: `__int64 __fastcall(HWND *this, HINSTANCE hInstance, DWORD dwExStyle, LPCWSTR lpClassName, LPCWSTR lpWindowName, DWORD dwStyle, int X, int Y, int nWidth, int nHeight, HWND hWndParent, HMENU hMenu, HICON, HICON, UINT)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180008294`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001349c`
- `0x18001c06c`
- `0x1800307a0`
- `0x1800310e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180030ae0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180030ae0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030ace`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030ace`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030a42`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x180030913`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x180030913`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x1800309f8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x1800309f8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassInfoExW` at `0x180030876`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassInfoExW` at `0x180030876`

## pseudocode

```c
__int64 __fastcall CMsgrWndBase::CreateMsgrWndCustom(
        HWND *this,
        HINSTANCE hInstance,
        DWORD dwExStyle,
        LPCWSTR lpClassName,
        LPCWSTR lpWindowName,
        DWORD dwStyle,
        int X,
        int Y,
        int nWidth,
        int nHeight,
        HWND hWndParent,
        HMENU hMenu,
        HICON a13,
        HICON a14,
        UINT a15)
{
  PVOID *v19; // rbx
  unsigned int v20; // esi
  signed int LastError; // eax
  __int64 v22; // rdx
  HWND Window; // rax
  __int64 v24; // rcx
  HWND v25; // r14
  HWND v26; // r15
  HWND v27; // rcx
  __int64 v28; // rax
  tagWNDCLASSEXW wcx; // [rsp+60h] [rbp-49h] BYREF

  v19 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids);
    v19 = (PVOID *)WPP_GLOBAL_Control;
  }
  v20 = 0;
  if ( !lpClassName )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
    v20 = -2147467259;
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids, 2147500037LL);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  memset_0(&wcx, 0, sizeof(wcx));
  wcx.cbSize = 80;
  if ( (v20 & 0x80000000) != 0 )
    goto LABEL_51;
  if ( !GetClassInfoExW(hInstance, lpClassName, &wcx) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids);
    }
    wcx.cbClsExtra = 0;
    wcx.lpfnWndProc = (WNDPROC)CMsgrWndBase::WndProc;
    wcx.hIcon = a13;
    wcx.hCursor = a14;
    wcx.style = a15;
    *(_OWORD *)&wcx.hbrBackground = 0;
    wcx.hIconSm = 0;
    wcx.cbSize = 80;
    wcx.cbWndExtra = 8;
    wcx.hInstance = hInstance;
    wcx.lpszClassName = lpClassName;
    if ( !RegisterClassExW(&wcx) )
    {
      v20 = -2147467259;
      v19 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v22 = 37;
LABEL_23:
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v22,
          WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids,
          (unsigned int)LastError);
        v19 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_51;
      }
      goto LABEL_51;
    }
    if ( ::hInstance )
      MicrosoftTelemetryAssertTriggeredNoArgs(0);
    ::hInstance = hInstance;
  }
  this[4] = hWndParent;
  Window = CreateWindowExW(
             dwExStyle,
             lpClassName,
             lpWindowName,
             dwStyle,
             X,
             Y,
             nWidth,
             nHeight,
             hWndParent,
             hMenu,
             hInstance,
             this);
  v25 = Window;
  if ( this[3] )
  {
    if ( Window != this[3] )
      MicrosoftTelemetryAssertTriggeredNoArgs(v24);
    v26 = this[3];
    v20 = v26 != v25 ? 0x80004005 : 0;
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids, v20);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v25 == v26 )
    {
      v27 = this[5];
      if ( v27 )
      {
        free(v27);
        this[5] = 0;
      }
      v28 = _o__wcsdup(lpWindowName);
      this[5] = (HWND)v28;
      if ( v28
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids, v28);
      }
      *((_BYTE *)this + 8) = 0;
      *((_BYTE *)this + 9) = 0;
      *((_BYTE *)this + 10) = 0;
      *((_BYTE *)this + 11) = 0;
      *((_BYTE *)this + 12) = 0;
      *((_BYTE *)this + 13) = 0;
      *((_BYTE *)this + 14) = 0;
      *((_BYTE *)this + 15) = 0;
      *((_BYTE *)this + 16) = 0;
      goto LABEL_53;
    }
  }
  else
  {
    if ( Window )
      MicrosoftTelemetryAssertTriggeredNoArgs(v24);
    v20 = -2147467259;
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v22 = 38;
      goto LABEL_23;
    }
  }
LABEL_51:
  if ( ::hInstance )
  {
    UnregisterClassFunc();
LABEL_53:
    v19 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 4) != 0 && *((_BYTE *)v19 + 25) >= 6u )
    WPP_SF_d(v19[2], 41, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids, v20);
  return v20;
}

```

## disassembly

```asm
0x1800307a0  push    rbp
0x1800307a2  push    rbx
0x1800307a3  push    rsi
0x1800307a4  push    rdi
0x1800307a5  push    r12
0x1800307a7  push    r14
0x1800307a9  push    r15
0x1800307ab  lea     rbp, [rsp-7]
0x1800307b0  sub     rsp, 0B0h
0x1800307b7  mov     r15, r9
0x1800307ba  mov     r12d, r8d
0x1800307bd  mov     r14, rdx
0x1800307c0  mov     rdi, rcx
0x1800307c3  mov     rbx, cs:WPP_GLOBAL_Control
0x1800307ca  lea     rax, WPP_GLOBAL_Control
0x1800307d1  cmp     rbx, rax
0x1800307d4  jz      short loc_1800307FE
0x1800307d6  test    byte ptr [rbx+1Ch], 4
0x1800307da  jz      short loc_1800307FE
0x1800307dc  cmp     byte ptr [rbx+19h], 6
0x1800307e0  jb      short loc_1800307FE
0x1800307e2  mov     rcx, [rbx+10h]
0x1800307e6  lea     r8, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids
0x1800307ed  mov     edx, 22h ; '"'
0x1800307f2  call    WPP_SF_
0x1800307f7  mov     rbx, cs:WPP_GLOBAL_Control
0x1800307fe  xor     esi, esi
0x180030800  test    r15, r15
0x180030803  jnz     short loc_18003084E
0x180030805  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003080a  mov     ecx, 80004005h
0x18003080f  mov     esi, ecx
0x180030811  mov     rbx, cs:WPP_GLOBAL_Control
0x180030818  lea     rax, WPP_GLOBAL_Control
0x18003081f  cmp     rbx, rax
0x180030822  jz      short loc_18003084E
0x180030824  test    byte ptr [rbx+1Ch], 4
0x180030828  jz      short loc_18003084E
0x18003082a  cmp     byte ptr [rbx+19h], 2
0x18003082e  jb      short loc_18003084E
0x180030830  mov     r9d, ecx
0x180030833  lea     edx, [r15+23h]
0x180030837  mov     rcx, [rbx+10h]
0x18003083b  lea     r8, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids
0x180030842  call    WPP_SF_d
0x180030847  mov     rbx, cs:WPP_GLOBAL_Control
0x18003084e  xor     edx, edx; Val
0x180030850  lea     rcx, [rbp+37h+wcx]; void *
0x180030854  lea     r8d, [rdx+50h]; Size
0x180030858  call    memset_0
0x18003085d  mov     [rbp+37h+wcx.cbSize], 50h ; 'P'
0x180030864  test    esi, esi
0x180030866  js      loc_180030B4E
0x18003086c  lea     r8, [rbp+37h+wcx]; lpwcx
0x180030870  mov     rdx, r15; lpszClass
0x180030873  mov     rcx, r14; hInstance
0x180030876  call    cs:__imp_GetClassInfoExW
0x18003087c  test    eax, eax
0x18003087e  jnz     loc_1800309A2
0x180030884  mov     rcx, cs:WPP_GLOBAL_Control
0x18003088b  lea     rax, WPP_GLOBAL_Control
0x180030892  cmp     rcx, rax
0x180030895  jz      short loc_1800308B8
0x180030897  test    byte ptr [rcx+1Ch], 4
0x18003089b  jz      short loc_1800308B8
0x18003089d  cmp     byte ptr [rcx+19h], 2
0x1800308a1  jb      short loc_1800308B8
0x1800308a3  mov     rcx, [rcx+10h]
0x1800308a7  lea     r8, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids
0x1800308ae  mov     edx, 24h ; '$'
0x1800308b3  call    WPP_SF_
0x1800308b8  lea     rax, ?WndProc@CMsgrWndBase@@KA_JPEAUHWND__@@I_K_J@Z; CMsgrWndBase::WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800308bf  mov     [rbp+37h+wcx.cbClsExtra], 0
0x1800308c6  mov     [rbp+37h+wcx.lpfnWndProc], rax
0x1800308ca  lea     rcx, [rbp+37h+wcx]; WNDCLASSEXW *
0x1800308ce  mov     rax, [rbp+37h+arg_60]
0x1800308d5  xorps   xmm0, xmm0
0x1800308d8  mov     [rbp+37h+wcx.hIcon], rax
0x1800308dc  mov     rax, [rbp+37h+arg_68]
0x1800308e3  mov     [rbp+37h+wcx.hCursor], rax
0x1800308e7  mov     eax, [rbp+37h+arg_70]
0x1800308ed  mov     [rbp+37h+wcx.style], eax
0x1800308f0  movdqa  xmmword ptr [rbp+37h+wcx.hbrBackground], xmm0
0x1800308f5  mov     [rbp+37h+wcx.hIconSm], 0
0x1800308fd  mov     [rbp+37h+wcx.cbSize], 50h ; 'P'
0x180030904  mov     [rbp+37h+wcx.cbWndExtra], 8
0x18003090b  mov     [rbp+37h+wcx.hInstance], r14
0x18003090f  mov     [rbp+37h+wcx.lpszClassName], r15
0x180030913  call    cs:__imp_RegisterClassExW
0x180030919  xor     ecx, ecx
0x18003091b  cmp     cx, ax
0x18003091e  jnz     short loc_18003098D
0x180030920  mov     esi, 80004005h
0x180030925  mov     rbx, cs:WPP_GLOBAL_Control
0x18003092c  lea     r12, WPP_GLOBAL_Control
0x180030933  cmp     rbx, r12
0x180030936  jz      loc_180030B55
0x18003093c  test    byte ptr [rbx+1Ch], 4
0x180030940  jz      loc_180030B55
0x180030946  cmp     byte ptr [rbx+19h], 2
0x18003094a  jb      loc_180030B55
0x180030950  call    cs:__imp_GetLastError
0x180030956  test    eax, eax
0x180030958  jle     short loc_180030962
0x18003095a  movzx   eax, ax
0x18003095d  or      eax, 80070000h
0x180030962  mov     edx, 25h ; '%'
0x180030967  mov     rcx, cs:WPP_GLOBAL_Control
0x18003096e  lea     r8, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids
0x180030975  mov     r9d, eax
0x180030978  mov     rcx, [rcx+10h]
0x18003097c  call    WPP_SF_d
0x180030981  mov     rbx, cs:WPP_GLOBAL_Control
0x180030988  jmp     loc_180030B55
0x18003098d  cmp     cs:hInstance, rcx
0x180030994  jz      short loc_18003099B
0x180030996  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003099b  mov     cs:hInstance, r14
0x1800309a2  mov     rcx, [rbp+37h+arg_50]
0x1800309a9  mov     rdx, r15; lpClassName
0x1800309ac  mov     rax, [rbp+37h+arg_58]
0x1800309b3  mov     r9d, [rbp+37h+dwStyle]; dwStyle
0x1800309b7  mov     r8, [rbp+37h+lpWindowName]; lpWindowName
0x1800309bb  mov     [rsp+0E0h+lpParam], rdi; lpParam
0x1800309c0  mov     [rsp+0E0h+hInstance], r14; hInstance
0x1800309c5  mov     [rsp+0E0h+hMenu], rax; hMenu
0x1800309ca  mov     eax, [rbp+37h+arg_48]
0x1800309d0  mov     [rsp+0E0h+hWndParent], rcx; hWndParent
0x1800309d5  mov     [rsp+0E0h+nHeight], eax; nHeight
0x1800309d9  mov     eax, [rbp+37h+arg_40]
0x1800309df  mov     [rsp+0E0h+nWidth], eax; nWidth
0x1800309e3  mov     eax, [rbp+37h+arg_38]
0x1800309e6  mov     [rsp+0E0h+Y], eax; Y
0x1800309ea  mov     eax, [rbp+37h+arg_30]
0x1800309ed  mov     [rdi+20h], rcx
0x1800309f1  mov     ecx, r12d; dwExStyle
0x1800309f4  mov     [rsp+0E0h+X], eax; X
0x1800309f8  call    cs:__imp_CreateWindowExW
0x1800309fe  cmp     qword ptr [rdi+18h], 0
0x180030a03  mov     r14, rax
0x180030a06  jnz     short loc_180030A5E
0x180030a08  test    rax, rax
0x180030a0b  jz      short loc_180030A12
0x180030a0d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180030a12  mov     esi, 80004005h
0x180030a17  mov     rbx, cs:WPP_GLOBAL_Control
0x180030a1e  lea     r12, WPP_GLOBAL_Control
0x180030a25  cmp     rbx, r12
0x180030a28  jz      loc_180030B55
0x180030a2e  test    byte ptr [rbx+1Ch], 4
0x180030a32  jz      loc_180030B55
0x180030a38  cmp     byte ptr [rbx+19h], 2
0x180030a3c  jb      loc_180030B55
0x180030a42  call    cs:__imp_GetLastError
0x180030a48  test    eax, eax
0x180030a4a  jle     short loc_180030A54
0x180030a4c  movzx   eax, ax
0x180030a4f  or      eax, 80070000h
0x180030a54  mov     edx, 26h ; '&'
0x180030a59  jmp     loc_180030967
0x180030a5e  cmp     r14, [rdi+18h]
0x180030a62  jz      short loc_180030A69
0x180030a64  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180030a69  mov     r15, [rdi+18h]
0x180030a6d  mov     rax, r14
0x180030a70  sub     rax, r15
0x180030a73  neg     rax
0x180030a76  sbb     esi, esi
0x180030a78  and     esi, 80004005h
0x180030a7e  mov     rbx, cs:WPP_GLOBAL_Control
0x180030a85  lea     r12, WPP_GLOBAL_Control
0x180030a8c  cmp     rbx, r12
0x180030a8f  jz      short loc_180030ABC
0x180030a91  test    byte ptr [rbx+1Ch], 4
0x180030a95  jz      short loc_180030ABC
0x180030a97  cmp     byte ptr [rbx+19h], 2
0x180030a9b  jb      short loc_180030ABC
0x180030a9d  mov     rcx, [rbx+10h]
0x180030aa1  lea     r8, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids
0x180030aa8  mov     edx, 27h ; '''
0x180030aad  mov     r9d, esi
0x180030ab0  call    WPP_SF_d
0x180030ab5  mov     rbx, cs:WPP_GLOBAL_Control
0x180030abc  cmp     r14, r15
0x180030abf  jnz     loc_180030B55
0x180030ac5  mov     rcx, [rdi+28h]; Block
0x180030ac9  test    rcx, rcx
0x180030acc  jz      short loc_180030ADC
0x180030ace  call    cs:__imp_free
0x180030ad4  mov     qword ptr [rdi+28h], 0
0x180030adc  mov     rcx, [rbp+37h+lpWindowName]
0x180030ae0  call    cs:__imp__o__wcsdup
0x180030ae6  mov     [rdi+28h], rax
0x180030aea  test    rax, rax
0x180030aed  jz      short loc_180030B1F
0x180030aef  mov     rcx, cs:WPP_GLOBAL_Control
0x180030af6  cmp     rcx, r12
0x180030af9  jz      short loc_180030B1F
0x180030afb  test    byte ptr [rcx+1Ch], 4
0x180030aff  jz      short loc_180030B1F
0x180030b01  cmp     byte ptr [rcx+19h], 5
0x180030b05  jb      short loc_180030B1F
0x180030b07  mov     rcx, [rcx+10h]
0x180030b0b  lea     r8, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids
0x180030b12  mov     edx, 28h ; '('
0x180030b17  mov     r9, rax
0x180030b1a  call    WPP_SF_S
0x180030b1f  xor     eax, eax
0x180030b21  xchg    al, [rdi+8]
0x180030b24  xor     eax, eax
0x180030b26  xchg    al, [rdi+9]
0x180030b29  xor     eax, eax
0x180030b2b  xchg    al, [rdi+0Ah]
0x180030b2e  xor     eax, eax
0x180030b30  xchg    al, [rdi+0Bh]
0x180030b33  xor     eax, eax
0x180030b35  xchg    al, [rdi+0Ch]
0x180030b38  xor     eax, eax
0x180030b3a  xchg    al, [rdi+0Dh]
0x180030b3d  xor     eax, eax
0x180030b3f  xchg    al, [rdi+0Eh]
0x180030b42  xor     eax, eax
0x180030b44  xchg    al, [rdi+0Fh]
0x180030b47  xor     eax, eax
0x180030b49  xchg    al, [rdi+10h]
0x180030b4c  jmp     short loc_180030B64
0x180030b4e  lea     r12, WPP_GLOBAL_Control
0x180030b55  cmp     cs:hInstance, 0
0x180030b5d  jz      short loc_180030B6B
0x180030b5f  call    ?UnregisterClassFunc@@YAXXZ; UnregisterClassFunc(void)
0x180030b64  mov     rbx, cs:WPP_GLOBAL_Control
0x180030b6b  cmp     rbx, r12
0x180030b6e  jz      short loc_180030B94
0x180030b70  test    byte ptr [rbx+1Ch], 4
0x180030b74  jz      short loc_180030B94
0x180030b76  cmp     byte ptr [rbx+19h], 6
0x180030b7a  jb      short loc_180030B94
0x180030b7c  mov     rcx, [rbx+10h]
0x180030b80  lea     r8, WPP_63ee413f9c5a3ea6c4f38a3bacab49d2_Traceguids
0x180030b87  mov     edx, 29h ; ')'
0x180030b8c  mov     r9d, esi
0x180030b8f  call    WPP_SF_d
0x180030b94  mov     eax, esi
0x180030b96  add     rsp, 0B0h
0x180030b9d  pop     r15
0x180030b9f  pop     r14
0x180030ba1  pop     r12
0x180030ba3  pop     rdi
0x180030ba4  pop     rsi
0x180030ba5  pop     rbx
0x180030ba6  pop     rbp
0x180030ba7  retn
```
