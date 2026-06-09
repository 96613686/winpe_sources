# PAL_System_Win32_ThreadCreateWindow(HWND__ * *)

- ea: `0x180036088`
- end: `0x18003634b`
- name: `?PAL_System_Win32_ThreadCreateWindow@@YAJPEAPEAUHWND__@@@Z`
- size: `707`
- prototype: `__int64 __fastcall(HWND *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800372e0`

## callees

- `0x1800010b0`
- `0x18000b8f8`
- `0x18000b98c`
- `0x180036088`
- `0x180036354`
- `0x180037208`
- `0x180047ebe`
- `0x180047ef0`

## import_xrefs

- `USER32!CreateWindowExW` at `0x18003629d`
- `USER32!CreateWindowExW` at `0x18003629d`

## string_xrefs

- `0x1800360ee`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x18003618c`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x1800362ce`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x1800360d3`: `PAL_System_Win32_ThreadCreateWindow`
- `0x180036171`: `PAL_System_Win32_ThreadCreateWindow`
- `0x1800362b3`: `PAL_System_Win32_ThreadCreateWindow`
- `0x18003619c`: `Failed to initialize thread window class`
- `0x1800362e2`: `Failed to create thread window`

## pseudocode

```c
__int64 __fastcall PAL_System_Win32_ThreadCreateWindow(HWND *a1, __int64 a2, int a3, int a4)
{
  int ModuleSpecificClassName; // ebx
  const unsigned __int16 *v6; // rcx
  unsigned int v7; // r8d
  int v8; // r9d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HWND Window; // rax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v15; // [rsp+60h] [rbp-A0h] BYREF
  int v16; // [rsp+64h] [rbp-9Ch] BYREF
  const char *v17; // [rsp+68h] [rbp-98h] BYREF
  const char *v18; // [rsp+70h] [rbp-90h] BYREF
  const char *v19; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ClassName[264]; // [rsp+80h] [rbp-80h] BYREF

  if ( a1 )
  {
    memset_0(ClassName, 0, 0x208u);
    ModuleSpecificClassName = PAL_System_Win32_ThreadRegisterWindowClass();
    if ( ModuleSpecificClassName >= 0 )
    {
      ModuleSpecificClassName = PAL_System_Win32_GetModuleSpecificClassName(v6, ClassName, v7);
      if ( ModuleSpecificClassName >= 0 )
      {
        Window = CreateWindowExW(0, ClassName, 0, 0, 0, 0, 0, 0, HWND_MESSAGE, 0, 0, 0);
        if ( Window )
        {
          *a1 = Window;
          return 0;
        }
        else if ( (unsigned int)dword_18005C008 > 2 )
        {
          v16 = 463;
          v19 = "PAL_System_Win32_ThreadCreateWindow";
          v15 = -2147467259;
          v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
          v17 = "Failed to create thread window";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v11,
            (unsigned int)byte_180054721,
            v12,
            v13,
            (__int64)&v17,
            (__int64)&v15,
            (__int64)&v18,
            (__int64)&v16,
            (__int64)&v19);
        }
      }
      else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
             && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          17,
          (unsigned int)WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"Failed to get module specific class name",
          ModuleSpecificClassName);
      }
    }
    else if ( (unsigned int)dword_18005C008 > 2 )
    {
      v16 = 447;
      v19 = "PAL_System_Win32_ThreadCreateWindow";
      v15 = ModuleSpecificClassName;
      v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
      v17 = "Failed to initialize thread window class";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        dword_18005C008,
        (unsigned int)&word_180054766,
        v7,
        v8,
        (__int64)&v17,
        (__int64)&v15,
        (__int64)&v18,
        (__int64)&v16,
        (__int64)&v19);
    }
  }
  else
  {
    ModuleSpecificClassName = -2147024809;
    if ( (unsigned int)dword_18005C008 > 2 )
    {
      v15 = 435;
      v17 = "PAL_System_Win32_ThreadCreateWindow";
      v16 = -2147024809;
      v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
      v19 = "NULL paramater passed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        0,
        (unsigned int)&byte_1800547F7,
        a3,
        a4,
        (__int64)&v19,
        (__int64)&v16,
        (__int64)&v18,
        (__int64)&v15,
        (__int64)&v17);
    }
  }
  return (unsigned int)ModuleSpecificClassName;
}

```

## disassembly

```asm
0x180036088  mov     [rsp-8+arg_8], rbx
0x18003608d  mov     [rsp-8+arg_10], rdi
0x180036092  push    rbp
0x180036093  lea     rbp, [rsp-1A0h]
0x18003609b  sub     rsp, 2A0h
0x1800360a2  mov     rax, cs:__security_cookie
0x1800360a9  xor     rax, rsp
0x1800360ac  mov     [rbp+1A0h+var_10], rax
0x1800360b3  mov     rdi, rcx
0x1800360b6  test    rcx, rcx
0x1800360b9  jnz     loc_180036146
0x1800360bf  mov     eax, cs:dword_18005C008
0x1800360c5  mov     ebx, 80070057h
0x1800360ca  cmp     eax, 2
0x1800360cd  jbe     loc_180036325
0x1800360d3  lea     rax, aPalSystemWin32_2; "PAL_System_Win32_ThreadCreateWindow"
0x1800360da  mov     [rsp+2A0h+var_240], 1B3h
0x1800360e2  mov     [rsp+2A0h+var_238], rax
0x1800360e7  lea     rdx, byte_1800547F7
0x1800360ee  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800360f5  mov     [rsp+2A0h+var_23C], ebx
0x1800360f9  mov     [rsp+2A0h+var_230], rax
0x1800360fe  lea     rax, aNullParamaterP; "NULL paramater passed"
0x180036105  mov     [rsp+2A0h+var_228], rax
0x18003610a  lea     rax, [rsp+2A0h+var_238]
0x18003610f  mov     [rsp+2A0h+hWndParent], rax
0x180036114  lea     rax, [rsp+2A0h+var_240]
0x180036119  mov     qword ptr [rsp+2A0h+nHeight], rax
0x18003611e  lea     rax, [rsp+2A0h+var_230]
0x180036123  mov     qword ptr [rsp+2A0h+nWidth], rax
0x180036128  lea     rax, [rsp+2A0h+var_23C]
0x18003612d  mov     qword ptr [rsp+2A0h+Y], rax
0x180036132  lea     rax, [rsp+2A0h+var_228]
0x180036137  mov     qword ptr [rsp+2A0h+X], rax
0x18003613c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180036141  jmp     loc_180036325
0x180036146  xor     edx, edx; Val
0x180036148  lea     rcx, [rbp+1A0h+ClassName]; void *
0x18003614c  mov     r8d, 208h; Size
0x180036152  call    memset_0
0x180036157  call    ?PAL_System_Win32_ThreadRegisterWindowClass@@YAJXZ; PAL_System_Win32_ThreadRegisterWindowClass(void)
0x18003615c  mov     ebx, eax
0x18003615e  test    eax, eax
0x180036160  jns     short loc_1800361DA
0x180036162  mov     ecx, cs:dword_18005C008
0x180036168  cmp     ecx, 2
0x18003616b  jbe     loc_180036325
0x180036171  lea     rax, aPalSystemWin32_2; "PAL_System_Win32_ThreadCreateWindow"
0x180036178  mov     [rsp+2A0h+var_23C], 1BFh
0x180036180  mov     [rsp+2A0h+var_228], rax
0x180036185  lea     rdx, word_180054766
0x18003618c  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180036193  mov     [rsp+2A0h+var_240], ebx
0x180036197  mov     [rsp+2A0h+var_230], rax
0x18003619c  lea     rax, aFailedToInitia_3; "Failed to initialize thread window clas"...
0x1800361a3  mov     [rsp+2A0h+var_238], rax
0x1800361a8  lea     rax, [rsp+2A0h+var_228]
0x1800361ad  mov     [rsp+2A0h+hWndParent], rax
0x1800361b2  lea     rax, [rsp+2A0h+var_23C]
0x1800361b7  mov     qword ptr [rsp+2A0h+nHeight], rax
0x1800361bc  lea     rax, [rsp+2A0h+var_230]
0x1800361c1  mov     qword ptr [rsp+2A0h+nWidth], rax
0x1800361c6  lea     rax, [rsp+2A0h+var_240]
0x1800361cb  mov     qword ptr [rsp+2A0h+Y], rax
0x1800361d0  lea     rax, [rsp+2A0h+var_238]
0x1800361d5  jmp     loc_180036137
0x1800361da  lea     rdx, [rbp+1A0h+ClassName]; unsigned __int16 *
0x1800361de  call    ?PAL_System_Win32_GetModuleSpecificClassName@@YAJPEBGPEAGK@Z; PAL_System_Win32_GetModuleSpecificClassName(ushort const *,ushort *,ulong)
0x1800361e3  mov     ebx, eax
0x1800361e5  test    eax, eax
0x1800361e7  jns     short loc_18003624D
0x1800361e9  mov     rax, cs:WPP_GLOBAL_Control
0x1800361f0  lea     rcx, WPP_GLOBAL_Control
0x1800361f7  cmp     rax, rcx
0x1800361fa  jz      loc_180036325
0x180036200  test    byte ptr [rax+1Ch], 8
0x180036204  jz      loc_180036325
0x18003620a  cmp     byte ptr [rax+19h], 2
0x18003620e  jb      loc_180036325
0x180036214  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180036219  lea     rcx, aFailedToGetMod; "Failed to get module specific class nam"...
0x180036220  mov     [rsp+2A0h+Y], ebx
0x180036224  mov     qword ptr [rsp+2A0h+X], rcx
0x180036229  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x180036230  mov     rcx, cs:WPP_GLOBAL_Control
0x180036237  mov     edx, 11h
0x18003623c  mov     r9d, eax
0x18003623f  mov     rcx, [rcx+10h]
0x180036243  call    WPP_SF_DsD
0x180036248  jmp     loc_180036325
0x18003624d  mov     [rsp+2A0h+lpParam], 0; lpParam
0x180036256  lea     rdx, [rbp+1A0h+ClassName]; lpClassName
0x18003625a  mov     [rsp+2A0h+hInstance], 0; hInstance
0x180036263  xor     r9d, r9d; dwStyle
0x180036266  mov     [rsp+2A0h+hMenu], 0; hMenu
0x18003626f  xor     r8d, r8d; lpWindowName
0x180036272  mov     [rsp+2A0h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x18003627b  xor     ecx, ecx; dwExStyle
0x18003627d  mov     [rsp+2A0h+nHeight], 0; nHeight
0x180036285  mov     [rsp+2A0h+nWidth], 0; nWidth
0x18003628d  mov     [rsp+2A0h+Y], 0; Y
0x180036295  mov     [rsp+2A0h+X], 0; X
0x18003629d  call    cs:__imp_CreateWindowExW
0x1800362a3  test    rax, rax
0x1800362a6  jnz     short loc_180036320
0x1800362a8  mov     eax, cs:dword_18005C008
0x1800362ae  cmp     eax, 2
0x1800362b1  jbe     short loc_180036325
0x1800362b3  lea     rax, aPalSystemWin32_2; "PAL_System_Win32_ThreadCreateWindow"
0x1800362ba  mov     [rsp+2A0h+var_23C], 1CFh
0x1800362c2  mov     [rsp+2A0h+var_228], rax
0x1800362c7  lea     rdx, byte_180054721
0x1800362ce  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800362d5  mov     [rsp+2A0h+var_240], 80004005h
0x1800362dd  mov     [rsp+2A0h+var_230], rax
0x1800362e2  lea     rax, aFailedToCreate_3; "Failed to create thread window"
0x1800362e9  mov     [rsp+2A0h+var_238], rax
0x1800362ee  lea     rax, [rsp+2A0h+var_228]
0x1800362f3  mov     [rsp+2A0h+hWndParent], rax
0x1800362f8  lea     rax, [rsp+2A0h+var_23C]
0x1800362fd  mov     qword ptr [rsp+2A0h+nHeight], rax
0x180036302  lea     rax, [rsp+2A0h+var_230]
0x180036307  mov     qword ptr [rsp+2A0h+nWidth], rax
0x18003630c  lea     rax, [rsp+2A0h+var_240]
0x180036311  mov     qword ptr [rsp+2A0h+Y], rax
0x180036316  lea     rax, [rsp+2A0h+var_238]
0x18003631b  jmp     loc_180036137
0x180036320  mov     [rdi], rax
0x180036323  xor     ebx, ebx
0x180036325  mov     eax, ebx
0x180036327  mov     rcx, [rbp+1A0h+var_10]
0x18003632e  xor     rcx, rsp; StackCookie
0x180036331  call    __security_check_cookie
0x180036336  lea     r11, [rsp+2A0h+var_s0]
0x18003633e  mov     rbx, [r11+18h]
0x180036342  mov     rdi, [r11+20h]
0x180036346  mov     rsp, r11
0x180036349  pop     rbp
0x18003634a  retn
```
