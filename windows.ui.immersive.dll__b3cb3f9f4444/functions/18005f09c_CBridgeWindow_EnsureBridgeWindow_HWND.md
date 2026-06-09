# CBridgeWindow::_EnsureBridgeWindow(HWND__ *)

- ea: `0x18005f09c`
- end: `0x18005f2d4`
- name: `?_EnsureBridgeWindow@CBridgeWindow@@AEAAJPEAUHWND__@@@Z`
- size: `568`
- prototype: `int(CBridgeWindow *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005f514`

## callees

- `0x180013f14`
- `0x18003d244`
- `0x180054ad4`
- `0x18005f09c`
- `0x1800e62cc`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005f0d8`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005f16e`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005f0d8`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005f16e`
- `USER32!CreateWindowExW` at `0x18005f292`
- `USER32!CreateWindowExW` at `0x18005f292`
- `USER32!RegisterClassW` at `0x18005f21a`
- `USER32!RegisterClassW` at `0x18005f21a`
- `USER32!GetAncestor` at `0x18005f1aa`
- `USER32!GetAncestor` at `0x18005f1aa`
- `USER32!LoadCursorW` at `0x18005f1f3`
- `USER32!LoadCursorW` at `0x18005f1f3`

## pseudocode

```c
__int64 __fastcall CBridgeWindow::_EnsureBridgeWindow(CBridgeWindow *this, HWND Ancestor)
{
  int Error; // ebx
  HANDLE Event; // rax
  HANDLE v6; // rax
  HCURSOR CursorW; // rax
  WNDCLASSW WndClass; // [rsp+60h] [rbp-9h] BYREF
  __int64 (__fastcall ***v10)(_QWORD, GUID *, char *); // [rsp+D0h] [rbp+67h] BYREF

  if ( *((_QWORD *)this + 14) )
  {
    return 0;
  }
  else
  {
    Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
    *((_QWORD *)this + 47) = Event;
    if ( Event || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease((char *)this + 328);
      *((_QWORD *)this + 41) = 0;
      v10 = 0;
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v10);
      Error = Microsoft::WRL::Details::MakeAndInitialize<CPlaybackManager,CPlaybackManager,>(&v10);
      if ( Error >= 0 )
        Error = (**v10)(v10, &GUID_1fc98738_e0bf_4cb2_9de2_20ab31b23ce4, (char *)this + 328);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v10);
      if ( Error >= 0 )
      {
        v6 = CreateEventExW(0, 0, 0, 0x1F0003u);
        *((_QWORD *)this + 48) = v6;
        Error = v6 ? 0 : ResultFromKnownLastError();
        if ( Error >= 0 )
        {
          if ( *((_BYTE *)this + 392) )
            Ancestor = GetAncestor(Ancestor, 2u);
          memset_0(&WndClass, 0, sizeof(WndClass));
          WndClass.style = 3;
          WndClass.lpfnWndProc = (WNDPROC)CImpWndProc::s_WndProc;
          WndClass.cbWndExtra = 8;
          WndClass.hInstance = &_ImageBase;
          CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
          WndClass.hbrBackground = (HBRUSH)6;
          WndClass.hCursor = CursorW;
          WndClass.lpszClassName = L"ApplicationHostBridgeWindow";
          RegisterClassW(&WndClass);
          if ( CreateWindowExW(
                 0x200000u,
                 WndClass.lpszClassName,
                 0,
                 0x80000000,
                 *((_DWORD *)this + 37),
                 *((_DWORD *)this + 38),
                 *((_DWORD *)this + 39) - *((_DWORD *)this + 37),
                 *((_DWORD *)this + 40) - *((_DWORD *)this + 38),
                 Ancestor,
                 0,
                 &_ImageBase,
                 (LPVOID)(((unsigned __int64)this + 104) & -(__int64)(this != 0))) )
          {
            Error = 0;
          }
          else
          {
            Error = ResultFromKnownLastError();
            if ( Error < 0 )
              return (unsigned int)Error;
          }
          *((_QWORD *)this + 22) = Ancestor;
        }
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18005f09c  mov     [rsp-8+arg_8], rbx
0x18005f0a1  mov     [rsp-8+arg_10], rsi
0x18005f0a6  push    rbp
0x18005f0a7  push    rdi
0x18005f0a8  push    r14
0x18005f0aa  lea     rbp, [rsp-47h]
0x18005f0af  sub     rsp, 0B0h
0x18005f0b6  cmp     qword ptr [rcx+70h], 0
0x18005f0bb  mov     rsi, rdx
0x18005f0be  mov     rdi, rcx
0x18005f0c1  jz      short loc_18005F0CA
0x18005f0c3  xor     ebx, ebx
0x18005f0c5  jmp     loc_18005F2B9
0x18005f0ca  xor     edx, edx; lpName
0x18005f0cc  xor     ecx, ecx; lpEventAttributes
0x18005f0ce  mov     r9d, 1F0003h; dwDesiredAccess
0x18005f0d4  lea     r8d, [rdx+1]; dwFlags
0x18005f0d8  call    cs:__imp_CreateEventExW
0x18005f0df  nop     dword ptr [rax+rax+00h]
0x18005f0e4  mov     [rdi+178h], rax
0x18005f0eb  test    rax, rax
0x18005f0ee  jnz     short loc_18005F0FF
0x18005f0f0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005f0f5  mov     ebx, eax
0x18005f0f7  test    eax, eax
0x18005f0f9  js      loc_18005F2B9
0x18005f0ff  lea     r14, [rdi+148h]
0x18005f106  mov     rcx, r14
0x18005f109  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18005f10e  lea     rcx, [rbp+57h+arg_0]
0x18005f112  mov     qword ptr [r14], 0
0x18005f119  mov     [rbp+57h+arg_0], 0
0x18005f121  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18005f126  lea     rcx, [rbp+57h+arg_0]
0x18005f12a  call    ??$MakeAndInitialize@VCPlaybackManager@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCPlaybackManager@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CPlaybackManager,CPlaybackManager,>(CPlaybackManager * *)
0x18005f12f  mov     ebx, eax
0x18005f131  test    eax, eax
0x18005f133  js      short loc_18005F150
0x18005f135  mov     rcx, [rbp+57h+arg_0]
0x18005f139  lea     rdx, _GUID_1fc98738_e0bf_4cb2_9de2_20ab31b23ce4
0x18005f140  mov     r8, r14
0x18005f143  mov     rax, [rcx]
0x18005f146  mov     rax, [rax]
0x18005f149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f14e  mov     ebx, eax
0x18005f150  lea     rcx, [rbp+57h+arg_0]
0x18005f154  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18005f159  test    ebx, ebx
0x18005f15b  js      loc_18005F2B9
0x18005f161  mov     r9d, 1F0003h; dwDesiredAccess
0x18005f167  xor     r8d, r8d; dwFlags
0x18005f16a  xor     edx, edx; lpName
0x18005f16c  xor     ecx, ecx; lpEventAttributes
0x18005f16e  call    cs:__imp_CreateEventExW
0x18005f175  nop     dword ptr [rax+rax+00h]
0x18005f17a  mov     [rdi+180h], rax
0x18005f181  test    rax, rax
0x18005f184  jnz     short loc_18005F18F
0x18005f186  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005f18b  mov     ebx, eax
0x18005f18d  jmp     short loc_18005F191
0x18005f18f  xor     ebx, ebx
0x18005f191  test    ebx, ebx
0x18005f193  js      loc_18005F2B9
0x18005f199  cmp     byte ptr [rdi+188h], 0
0x18005f1a0  jz      short loc_18005F1B9
0x18005f1a2  mov     edx, 2; gaFlags
0x18005f1a7  mov     rcx, rsi; hwnd
0x18005f1aa  call    cs:__imp_GetAncestor
0x18005f1b1  nop     dword ptr [rax+rax+00h]
0x18005f1b6  mov     rsi, rax
0x18005f1b9  xor     edx, edx; Val
0x18005f1bb  lea     rcx, [rbp+57h+WndClass]; void *
0x18005f1bf  lea     r8d, [rdx+48h]; Size
0x18005f1c3  call    memset_0
0x18005f1c8  lea     rax, ?s_WndProc@CImpWndProc@@KA_JPEAUHWND__@@I_K_J@Z; CImpWndProc::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18005f1cf  mov     [rbp+57h+WndClass.style], 3
0x18005f1d6  lea     rbx, __ImageBase
0x18005f1dd  mov     [rbp+57h+WndClass.lpfnWndProc], rax
0x18005f1e1  mov     edx, 7F00h; lpCursorName
0x18005f1e6  mov     [rbp+57h+WndClass.cbWndExtra], 8
0x18005f1ed  xor     ecx, ecx; hInstance
0x18005f1ef  mov     [rbp+57h+WndClass.hInstance], rbx
0x18005f1f3  call    cs:__imp_LoadCursorW
0x18005f1fa  nop     dword ptr [rax+rax+00h]
0x18005f1ff  lea     rcx, [rbp+57h+WndClass]; lpWndClass
0x18005f203  mov     [rbp+57h+WndClass.hbrBackground], 6
0x18005f20b  mov     [rbp+57h+WndClass.hCursor], rax
0x18005f20f  lea     rax, aApplicationhos; "ApplicationHostBridgeWindow"
0x18005f216  mov     [rbp+57h+WndClass.lpszClassName], rax
0x18005f21a  call    cs:__imp_RegisterClassW
0x18005f221  nop     dword ptr [rax+rax+00h]
0x18005f226  mov     r8d, [rdi+98h]
0x18005f22d  lea     rcx, [rdi+68h]
0x18005f231  mov     r9d, [rdi+94h]
0x18005f238  mov     rax, rdi
0x18005f23b  neg     rax
0x18005f23e  mov     eax, [rdi+9Ch]
0x18005f244  sbb     rdx, rdx
0x18005f247  sub     eax, r9d
0x18005f24a  and     rdx, rcx
0x18005f24d  mov     ecx, [rdi+0A0h]
0x18005f253  mov     [rsp+0C0h+lpParam], rdx; lpParam
0x18005f258  sub     ecx, r8d
0x18005f25b  mov     rdx, [rbp+57h+WndClass.lpszClassName]; lpClassName
0x18005f25f  mov     [rsp+0C0h+hInstance], rbx; hInstance
0x18005f264  mov     [rsp+0C0h+hMenu], 0; hMenu
0x18005f26d  mov     [rsp+0C0h+hWndParent], rsi; hWndParent
0x18005f272  mov     [rsp+0C0h+nHeight], ecx; nHeight
0x18005f276  mov     ecx, 200000h; dwExStyle
0x18005f27b  mov     [rsp+0C0h+nWidth], eax; nWidth
0x18005f27f  mov     [rsp+0C0h+Y], r8d; Y
0x18005f284  xor     r8d, r8d; lpWindowName
0x18005f287  mov     [rsp+0C0h+X], r9d; X
0x18005f28c  mov     r9d, 80000000h; dwStyle
0x18005f292  call    cs:__imp_CreateWindowExW
0x18005f299  nop     dword ptr [rax+rax+00h]
0x18005f29e  test    rax, rax
0x18005f2a1  jz      short loc_18005F2A7
0x18005f2a3  xor     ebx, ebx
0x18005f2a5  jmp     short loc_18005F2B2
0x18005f2a7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005f2ac  mov     ebx, eax
0x18005f2ae  test    eax, eax
0x18005f2b0  js      short loc_18005F2B9
0x18005f2b2  mov     [rdi+0B0h], rsi
0x18005f2b9  lea     r11, [rsp+0C0h+var_10]
0x18005f2c1  mov     eax, ebx
0x18005f2c3  mov     rbx, [r11+28h]
0x18005f2c7  mov     rsi, [r11+30h]
0x18005f2cb  mov     rsp, r11
0x18005f2ce  pop     r14
0x18005f2d0  pop     rdi
0x18005f2d1  pop     rbp
0x18005f2d2  retn
```
