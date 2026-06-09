# CFciPropertiesShellExt::ThreadProcStatic<{CFciPropertiesShellExt::ApplyThreadProc(void),0},0>(void *)

- ea: `0x180002960`
- end: `0x180002b07`
- name: `??$ThreadProcStatic@$H?ApplyThreadProc@CFciPropertiesShellExt@@AEAAXXZA@$0A@@CFciPropertiesShellExt@@CAKPEAX@Z`
- size: `423`
- prototype: `__int64 __fastcall(CFciPropertiesShellExt *Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002960`
- `0x1800061d0`
- `0x1800083e0`
- `0x18000d368`
- `0x18001623c`
- `0x180016564`
- `0x180018f68`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180002a74`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180002a74`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180002a18`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180002a18`

## string_xrefs

- `0x18000299d`: `CFciPropertiesShellExt::ThreadProcStatic`

## pseudocode

```c
__int64 __fastcall CFciPropertiesShellExt::ThreadProcStatic<{private: void CFciPropertiesShellExt::ApplyThreadProc(void),0},0>(
        CFciPropertiesShellExt *Parameter)
{
  HRESULT v2; // eax
  unsigned int v3; // edi
  int Hr; // eax
  char v6; // al
  int v7; // [rsp+44h] [rbp-184h] BYREF
  CFciPropertiesShellExt *v8; // [rsp+48h] [rbp-180h]
  void (__fastcall *v9)(CFciPropertiesShellExt *); // [rsp+50h] [rbp-178h]
  int v10; // [rsp+58h] [rbp-170h]
  _com_error *v11; // [rsp+60h] [rbp-168h] BYREF
  const exception *v12; // [rsp+68h] [rbp-160h] BYREF
  _QWORD v13[3]; // [rsp+70h] [rbp-158h] BYREF
  int v14; // [rsp+88h] [rbp-140h]
  int v15; // [rsp+8Ch] [rbp-13Ch]
  int v16; // [rsp+90h] [rbp-138h]
  char v17[96]; // [rsp+98h] [rbp-130h] BYREF
  int v18; // [rsp+F8h] [rbp-D0h]
  void **v19; // [rsp+100h] [rbp-C8h] BYREF
  HRESULT v20; // [rsp+108h] [rbp-C0h]
  unsigned int v21; // [rsp+12Ch] [rbp-9Ch]

  v8 = Parameter;
  v9 = (void (__fastcall *)(CFciPropertiesShellExt *))v13;
  v13[0] = L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.h";
  v13[1] = L"CFciPropertiesShellExt::ThreadProcStatic";
  v13[2] = L"FCIPROPH";
  v14 = 1051;
  v15 = 17;
  v16 = 255;
  v18 = 0x1000000;
  memset_0(v17, 0, sizeof(v17));
  CSrmFunctionTracer::CSrmFunctionTracer(&v19, v13, 0);
  try
  {
    v2 = CoInitializeEx(0, 0);
    v20 = v2;
    if ( v2 < 0 )
    {
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v19);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v19, Hr);
      v6 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v19);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v19, 0x425u, v6, 0);
    }
    v20 = v2;
    v9 = CFciPropertiesShellExt::ApplyThreadProc;
    v10 = 0;
    CFciPropertiesShellExt::ApplyThreadProc(Parameter);
    v20 = 0;
  }
  catch ( long v7 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v19,
      v7,
      L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.h",
      L"FCIPROPH",
      L"CFciPropertiesShellExt::ThreadProcStatic",
      0x42Du,
      v21);
  }
  catch ( _com_error *v11 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v19,
      v11,
      L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.h",
      L"FCIPROPH",
      L"CFciPropertiesShellExt::ThreadProcStatic",
      0x42Du,
      v21);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v19,
      L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.h",
      L"FCIPROPH",
      L"CFciPropertiesShellExt::ThreadProcStatic",
      0x42Du,
      v21);
  }
  catch ( const exception *v12 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v19,
      v12,
      L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.h",
      L"FCIPROPH",
      L"CFciPropertiesShellExt::ThreadProcStatic",
      0x42Du,
      v21);
  }
  v2 = CoInitializeEx(0, 0);
  v20 = v2;
  if ( v2 < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v19);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v19, Hr);
    v6 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v19);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v19, 0x425u, v6, 0);
  }
  v20 = v2;
  v9 = CFciPropertiesShellExt::ApplyThreadProc;
  v10 = 0;
}

```

## disassembly

```asm
0x180002960  mov     [rsp+arg_8], rbx
0x180002965  push    rdi
0x180002966  sub     rsp, 1C0h
0x18000296d  mov     rax, cs:__security_cookie
0x180002974  xor     rax, rsp
0x180002977  mov     [rsp+1C8h+var_18], rax
0x18000297f  mov     rdi, rcx
0x180002982  mov     [rsp+1C8h+var_180], rcx
0x180002987  lea     rax, [rsp+1C8h+var_158]
0x18000298c  mov     [rsp+1C8h+var_178], rax
0x180002991  lea     rax, aBaseFsFsrmClie_0; "base\\fs\\fsrm\\clients\\srmshell\\fcip"...
0x180002998  mov     [rsp+1C8h+var_158], rax
0x18000299d  lea     rax, aCfciproperties_0; "CFciPropertiesShellExt::ThreadProcStati"...
0x1800029a4  mov     [rsp+1C8h+var_150], rax
0x1800029a9  lea     rax, aFciproph; "FCIPROPH"
0x1800029b0  mov     [rsp+1C8h+var_148], rax
0x1800029b8  mov     [rsp+1C8h+var_140], 41Bh
0x1800029c3  mov     [rsp+1C8h+var_13C], 11h
0x1800029ce  mov     [rsp+1C8h+var_138], 0FFh
0x1800029d9  xor     ebx, ebx
0x1800029db  mov     [rsp+1C8h+var_D0], 1000000h
0x1800029e6  xor     edx, edx; Val
0x1800029e8  lea     r8d, [rbx+60h]; Size
0x1800029ec  lea     rcx, [rsp+1C8h+var_130]; void *
0x1800029f4  call    memset_0
0x1800029f9  nop
0x1800029fa  xor     r8d, r8d
0x1800029fd  lea     rdx, [rsp+1C8h+var_158]
0x180002a02  lea     rcx, [rsp+1C8h+var_C8]
0x180002a0a  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180002a0f  nop
0x180002a10  mov     [rsp+1C8h+var_188], bl
0x180002a14  xor     edx, edx; dwCoInit
0x180002a16  xor     ecx, ecx; pvReserved
0x180002a18  call    cs:__imp_CoInitializeEx
0x180002a1e  mov     [rsp+1C8h+var_C0], eax
0x180002a25  test    eax, eax
0x180002a27  js      loc_180002AC4
0x180002a2d  mov     [rsp+1C8h+var_C0], eax
0x180002a34  mov     [rsp+1C8h+var_188], 1
0x180002a39  lea     rax, ?ApplyThreadProc@CFciPropertiesShellExt@@AEAAXXZ; CFciPropertiesShellExt::ApplyThreadProc(void)
0x180002a40  mov     [rsp+1C8h+var_178], rax
0x180002a45  mov     [rsp+1C8h+var_170], ebx
0x180002a49  mov     rcx, rdi; this
0x180002a4c  call    ?ApplyThreadProc@CFciPropertiesShellExt@@AEAAXXZ; CFciPropertiesShellExt::ApplyThreadProc(void)
0x180002a51  mov     [rsp+1C8h+var_C0], ebx
0x180002a58  jmp     short loc_180002A5C
0x180002a5a  xor     ebx, ebx
0x180002a5c  mov     edi, [rsp+1C8h+var_C0]
0x180002a63  mov     rax, [rsp+1C8h+var_180]
0x180002a68  mov     [rax+0A8h], edi
0x180002a6e  cmp     [rsp+1C8h+var_188], bl
0x180002a72  jz      short loc_180002A81
0x180002a74  call    cs:__imp_CoUninitialize
0x180002a7a  mov     edi, [rsp+1C8h+var_C0]
0x180002a81  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180002a88  mov     [rsp+1C8h+var_C8], rax
0x180002a90  lea     rcx, [rsp+1C8h+var_C8]; this
0x180002a98  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180002a9d  mov     eax, edi
0x180002a9f  mov     rcx, [rsp+1C8h+var_18]
0x180002aa7  xor     rcx, rsp; StackCookie
0x180002aaa  call    __security_check_cookie
0x180002aaf  mov     rbx, [rsp+1C8h+arg_8]
0x180002ab7  add     rsp, 1C0h
0x180002abe  pop     rdi
0x180002abf  retn
0x180002ac0  jmp     short loc_180002A5A
0x180002ac2  jmp     short loc_180002A5A
0x180002ac4  lea     rcx, [rsp+1C8h+var_C8]; this
0x180002acc  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180002ad1  mov     edx, eax; int
0x180002ad3  lea     rcx, [rsp+1C8h+var_C8]; this
0x180002adb  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180002ae0  lea     rcx, [rsp+1C8h+var_C8]; this
0x180002ae8  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180002aed  mov     r8d, eax; char
0x180002af0  xor     r9d, r9d; unsigned __int16 *
0x180002af3  mov     edx, 425h; unsigned int
0x180002af8  lea     rcx, [rsp+1C8h+var_C8]; this
0x180002b00  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
