# CFciPropertiesShellExt::ThreadProcStatic<{CFciPropertiesShellExt::InitializeThreadProc(void),0},32768>(void *)

- ea: `0x180002b10`
- end: `0x180002cdc`
- name: `??$ThreadProcStatic@$H?InitializeThreadProc@CFciPropertiesShellExt@@AEAAXXZA@$0IAAA@@CFciPropertiesShellExt@@CAKPEAX@Z`
- size: `460`
- prototype: `__int64 __fastcall(HWND *Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002b10`
- `0x1800083e0`
- `0x180009ba0`
- `0x18000d368`
- `0x18001623c`
- `0x180016564`
- `0x180018f68`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180002c26`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180002c26`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180002bca`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180002bca`
- `USER32!PostMessageW` at `0x180002c43`
- `USER32!PostMessageW` at `0x180002c43`

## string_xrefs

- `0x180002b4f`: `CFciPropertiesShellExt::ThreadProcStatic`

## pseudocode

```c
__int64 __fastcall CFciPropertiesShellExt::ThreadProcStatic<{private: void CFciPropertiesShellExt::InitializeThreadProc(void),0},32768>(
        HWND *Parameter)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  int Hr; // eax
  char v6; // al
  int v8; // [rsp+50h] [rbp-188h] BYREF
  void (__fastcall *v9)(CFciPropertiesShellExt *__hidden); // [rsp+58h] [rbp-180h]
  int v10; // [rsp+60h] [rbp-178h]
  _com_error *v11; // [rsp+68h] [rbp-170h] BYREF
  const exception *v12; // [rsp+70h] [rbp-168h] BYREF
  _QWORD v13[3]; // [rsp+78h] [rbp-160h] BYREF
  int v14; // [rsp+90h] [rbp-148h]
  int v15; // [rsp+94h] [rbp-144h]
  int v16; // [rsp+98h] [rbp-140h]
  _DWORD v17[28]; // [rsp+A0h] [rbp-138h] BYREF
  void **v18; // [rsp+110h] [rbp-C8h] BYREF
  HRESULT v19; // [rsp+118h] [rbp-C0h]
  unsigned int v20; // [rsp+13Ch] [rbp-9Ch]

  v9 = (void (__fastcall *)(CFciPropertiesShellExt *__hidden))v13;
  v13[0] = L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.h";
  v13[1] = L"CFciPropertiesShellExt::ThreadProcStatic";
  v13[2] = L"FCIPROPH";
  v14 = 1051;
  v15 = 17;
  v16 = 255;
  v17[24] = 0x1000000;
  memset_0(v17, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer(&v18, v13, 0);
  try
  {
    v2 = CoInitializeEx(0, 0);
    v19 = v2;
    if ( v2 < 0 )
    {
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v18);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v18, Hr);
      v6 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v18);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v18, 0x425u, v6, 0);
    }
    v19 = v2;
    v9 = CFciPropertiesShellExt::InitializeThreadProc;
    v10 = 0;
    CFciPropertiesShellExt::InitializeThreadProc((CFciPropertiesShellExt *)Parameter);
    v19 = 0;
  }
  catch ( long v8 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v18,
      v8,
      L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.h",
      L"FCIPROPH",
      L"CFciPropertiesShellExt::ThreadProcStatic",
      0x42Du,
      v20);
  }
  catch ( _com_error *v11 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v18,
      v11,
      L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.h",
      L"FCIPROPH",
      L"CFciPropertiesShellExt::ThreadProcStatic",
      0x42Du,
      v20);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v18,
      L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.h",
      L"FCIPROPH",
      L"CFciPropertiesShellExt::ThreadProcStatic",
      0x42Du,
      v20);
  }
  catch ( const exception *v12 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v18,
      v12,
      L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.h",
      L"FCIPROPH",
      L"CFciPropertiesShellExt::ThreadProcStatic",
      0x42Du,
      v20);
  }
  v2 = CoInitializeEx(0, 0);
  v19 = v2;
  if ( v2 < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v18);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v18, Hr);
    v6 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v18);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v18, 0x425u, v6, 0);
  }
  v19 = v2;
  v9 = CFciPropertiesShellExt::InitializeThreadProc;
  v10 = 0;
  CFciPropertiesShellExt::InitializeThreadProc((CFciPropertiesShellExt *)Parameter);
}

```

## disassembly

```asm
0x180002b10  mov     r11, rsp
0x180002b13  mov     [r11+10h], rbx
0x180002b17  push    rdi
0x180002b18  sub     rsp, 1D0h
0x180002b1f  mov     rax, cs:__security_cookie
0x180002b26  xor     rax, rsp
0x180002b29  mov     [rsp+1D8h+var_18], rax
0x180002b31  mov     rdi, rcx
0x180002b34  mov     [rsp+1D8h+var_190], rcx
0x180002b39  lea     rax, [rsp+1D8h+var_160]
0x180002b3e  mov     [rsp+1D8h+var_180], rax
0x180002b43  lea     rax, aBaseFsFsrmClie_0; "base\\fs\\fsrm\\clients\\srmshell\\fcip"...
0x180002b4a  mov     [rsp+1D8h+var_160], rax
0x180002b4f  lea     rax, aCfciproperties_0; "CFciPropertiesShellExt::ThreadProcStati"...
0x180002b56  mov     [r11-158h], rax
0x180002b5d  lea     rax, aFciproph; "FCIPROPH"
0x180002b64  mov     [r11-150h], rax
0x180002b6b  mov     [rsp+1D8h+var_148], 41Bh
0x180002b76  mov     [rsp+1D8h+var_144], 11h
0x180002b81  mov     [rsp+1D8h+var_140], 0FFh
0x180002b8c  xor     ebx, ebx
0x180002b8e  mov     [rsp+1D8h+var_D8], 1000000h
0x180002b99  xor     edx, edx; Val
0x180002b9b  lea     r8d, [rbx+60h]; Size
0x180002b9f  lea     rcx, [r11-138h]; void *
0x180002ba6  call    memset_0
0x180002bab  nop
0x180002bac  xor     r8d, r8d
0x180002baf  lea     rdx, [rsp+1D8h+var_160]
0x180002bb4  lea     rcx, [rsp+1D8h+var_C8]
0x180002bbc  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180002bc1  nop
0x180002bc2  mov     [rsp+1D8h+var_198], bl
0x180002bc6  xor     edx, edx; dwCoInit
0x180002bc8  xor     ecx, ecx; pvReserved
0x180002bca  call    cs:__imp_CoInitializeEx
0x180002bd0  mov     [rsp+1D8h+var_C0], eax
0x180002bd7  test    eax, eax
0x180002bd9  js      loc_180002C99
0x180002bdf  mov     [rsp+1D8h+var_C0], eax
0x180002be6  mov     [rsp+1D8h+var_198], 1
0x180002beb  lea     rax, ?InitializeThreadProc@CFciPropertiesShellExt@@AEAAXXZ; CFciPropertiesShellExt::InitializeThreadProc(void)
0x180002bf2  mov     [rsp+1D8h+var_180], rax
0x180002bf7  mov     [rsp+1D8h+var_178], ebx
0x180002bfb  mov     rcx, rdi; this
0x180002bfe  call    ?InitializeThreadProc@CFciPropertiesShellExt@@AEAAXXZ; CFciPropertiesShellExt::InitializeThreadProc(void)
0x180002c03  mov     [rsp+1D8h+var_C0], ebx
0x180002c0a  jmp     short loc_180002C0E
0x180002c0c  xor     ebx, ebx
0x180002c0e  mov     ecx, [rsp+1D8h+var_C0]
0x180002c15  mov     rax, [rsp+1D8h+var_190]
0x180002c1a  mov     [rax+0A8h], ecx
0x180002c20  cmp     [rsp+1D8h+var_198], bl
0x180002c24  jz      short loc_180002C2C
0x180002c26  call    cs:__imp_CoUninitialize
0x180002c2c  xor     r9d, r9d; lParam
0x180002c2f  xor     r8d, r8d; wParam
0x180002c32  mov     edx, 8000h; Msg
0x180002c37  mov     rcx, [rsp+1D8h+var_190]
0x180002c3c  mov     rcx, [rcx+0A0h]; hWnd
0x180002c43  call    cs:__imp_PostMessageW
0x180002c49  mov     ebx, [rsp+1D8h+var_C0]
0x180002c50  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180002c57  mov     [rsp+1D8h+var_C8], rax
0x180002c5f  lea     rcx, [rsp+1D8h+var_C8]; this
0x180002c67  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180002c6c  mov     eax, ebx
0x180002c6e  mov     rcx, [rsp+1D8h+var_18]
0x180002c76  xor     rcx, rsp; StackCookie
0x180002c79  call    __security_check_cookie
0x180002c7e  mov     rbx, [rsp+1D8h+arg_8]
0x180002c86  add     rsp, 1D0h
0x180002c8d  pop     rdi
0x180002c8e  retn
0x180002c8f  jmp     loc_180002C0C
0x180002c94  jmp     loc_180002C0C
0x180002c99  lea     rcx, [rsp+1D8h+var_C8]; this
0x180002ca1  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180002ca6  mov     edx, eax; int
0x180002ca8  lea     rcx, [rsp+1D8h+var_C8]; this
0x180002cb0  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180002cb5  lea     rcx, [rsp+1D8h+var_C8]; this
0x180002cbd  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180002cc2  mov     r8d, eax; char
0x180002cc5  xor     r9d, r9d; unsigned __int16 *
0x180002cc8  mov     edx, 425h; unsigned int
0x180002ccd  lea     rcx, [rsp+1D8h+var_C8]; this
0x180002cd5  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
