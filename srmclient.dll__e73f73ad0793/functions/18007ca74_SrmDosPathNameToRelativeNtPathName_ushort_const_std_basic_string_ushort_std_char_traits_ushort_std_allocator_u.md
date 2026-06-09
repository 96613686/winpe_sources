# SrmDosPathNameToRelativeNtPathName(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18007ca74`
- end: `0x18007cc35`
- name: `?SrmDosPathNameToRelativeNtPathName@@YAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `449`
- prototype: `__int64 __fastcall(PCWSTR DosName, void *)`
- caller_count: `3`
- callee_count: `10`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18005ba58`
- `0x18005e5a8`
- `0x18007c16c`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x180010bc4`
- `0x18006febc`
- `0x1800700b8`
- `0x180072a80`
- `0x180073a80`
- `0x18007ca74`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18007cb99`
- `ntdll!RtlFreeHeap` at `0x18007cb99`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18007cb55`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18007cb55`

## string_xrefs

- `0x18007caa9`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007cac1`: `SRMPATHC`
- `0x18007cab5`: `SrmDosPathNameToRelativeNtPathName`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall SrmDosPathNameToRelativeNtPathName(PCWSTR DosName, _QWORD *a2)
{
  _WORD *v4; // rax
  char Hr; // al
  struct _UNICODE_STRING NtName; // [rsp+40h] [rbp-188h] BYREF
  int v7; // [rsp+50h] [rbp-178h] BYREF
  _QWORD *v8; // [rsp+58h] [rbp-170h]
  _com_error *v9; // [rsp+60h] [rbp-168h] BYREF
  const exception *v10; // [rsp+68h] [rbp-160h] BYREF
  _QWORD v11[4]; // [rsp+70h] [rbp-158h] BYREF
  int v12; // [rsp+90h] [rbp-138h]
  _DWORD v13[26]; // [rsp+98h] [rbp-130h] BYREF
  void **v14; // [rsp+100h] [rbp-C8h] BYREF
  int v15; // [rsp+108h] [rbp-C0h]
  unsigned int v16; // [rsp+12Ch] [rbp-9Ch]

  v8 = v11;
  v11[0] = L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp";
  v11[1] = L"SrmDosPathNameToRelativeNtPathName";
  v11[2] = L"SRMPATHC";
  v11[3] = 979;
  v12 = 255;
  v13[24] = 0x1000000;
  memset_0(v13, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v14, (const struct CSrmDebugInfo *)v11, 0);
  if ( a2[3] < 8u )
    v4 = a2;
  else
    v4 = (_WORD *)*a2;
  a2[2] = 0;
  *v4 = 0;
  NtName = 0;
  if ( !RtlDosPathNameToRelativeNtPathName_U(DosName, &NtName, 0, 0) )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v14, -2147200255);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v14);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v14, 0x3D9u, Hr, 0);
  }
  v15 = 0;
  try
  {
    std::wstring::assign(a2, NtName.Buffer);
  }
  catch ( long v7 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v14,
      v7,
      L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp",
      L"SRMPATHC",
      L"SrmDosPathNameToRelativeNtPathName",
      0x3E2u,
      v16);
  }
  catch ( _com_error *v9 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v14,
      v9,
      L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp",
      L"SRMPATHC",
      L"SrmDosPathNameToRelativeNtPathName",
      0x3E2u,
      v16);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v14,
      L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp",
      L"SRMPATHC",
      L"SrmDosPathNameToRelativeNtPathName",
      0x3E2u,
      v16);
  }
  catch ( const exception *v10 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v14,
      v10,
      L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp",
      L"SRMPATHC",
      L"SrmDosPathNameToRelativeNtPathName",
      0x3E2u,
      v16);
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtName.Buffer);
  if ( v15 < 0 )
    CSrmFunctionTracer::ReThrow((CSrmFunctionTracer *)&v14);
  v14 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v14);
}

```

## disassembly

```asm
0x18007ca74  mov     r11, rsp
0x18007ca77  mov     [r11+18h], rbx
0x18007ca7b  mov     [r11+20h], rsi
0x18007ca7f  push    rdi
0x18007ca80  sub     rsp, 1C0h
0x18007ca87  mov     rax, cs:__security_cookie
0x18007ca8e  xor     rax, rsp
0x18007ca91  mov     [rsp+1C8h+var_18], rax
0x18007ca99  mov     rdi, rdx
0x18007ca9c  mov     rsi, rcx
0x18007ca9f  lea     rax, [rsp+1C8h+var_158]
0x18007caa4  mov     [rsp+1C8h+var_170], rax
0x18007caa9  lea     rax, aBaseFsFsrmUtil_6; "base\\fs\\fsrm\\utilities\\path\\srmpat"...
0x18007cab0  mov     [rsp+1C8h+var_158], rax
0x18007cab5  lea     rax, aSrmdospathname; "SrmDosPathNameToRelativeNtPathName"
0x18007cabc  mov     [rsp+1C8h+var_150], rax
0x18007cac1  lea     rax, aSrmpathc; "SRMPATHC"
0x18007cac8  mov     [r11-148h], rax
0x18007cacf  mov     qword ptr [r11-140h], 3D3h
0x18007cada  xor     ebx, ebx
0x18007cadc  mov     [rsp+1C8h+var_138], 0FFh
0x18007cae7  mov     [rsp+1C8h+var_D0], 1000000h
0x18007caf2  xor     edx, edx; Val
0x18007caf4  lea     r8d, [rbx+60h]; Size
0x18007caf8  lea     rcx, [r11-130h]; void *
0x18007caff  call    memset_0
0x18007cb04  nop
0x18007cb05  xor     r8d, r8d
0x18007cb08  lea     rdx, [rsp+1C8h+var_158]
0x18007cb0d  lea     rcx, [rsp+1C8h+var_C8]
0x18007cb15  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007cb1a  nop
0x18007cb1b  cmp     qword ptr [rdi+18h], 8
0x18007cb20  jb      short loc_18007CB27
0x18007cb22  mov     rax, [rdi]
0x18007cb25  jmp     short loc_18007CB2A
0x18007cb27  mov     rax, rdi
0x18007cb2a  mov     [rdi+10h], rbx
0x18007cb2e  mov     [rax], bx
0x18007cb31  xorps   xmm0, xmm0
0x18007cb34  movups  xmmword ptr [rsp+1C8h+NtName.Length], xmm0
0x18007cb39  mov     eax, [rsp+1C8h+var_C0]
0x18007cb40  mov     [rsp+1C8h+var_C0], eax
0x18007cb47  xor     r9d, r9d; RelativeName
0x18007cb4a  xor     r8d, r8d; PartName
0x18007cb4d  lea     rdx, [rsp+1C8h+NtName]; NtName
0x18007cb52  mov     rcx, rsi; DosName
0x18007cb55  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18007cb5b  test    al, al
0x18007cb5d  jz      loc_18007CBEF
0x18007cb63  mov     [rsp+1C8h+var_C0], ebx
0x18007cb6a  movzx   r8d, [rsp+1C8h+NtName.Length]
0x18007cb70  shr     r8, 1
0x18007cb73  mov     rdx, [rsp+1C8h+NtName.Buffer]; Src
0x18007cb78  mov     rcx, rdi; void *
0x18007cb7b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18007cb80  nop
0x18007cb81  jmp     short loc_18007CB85
0x18007cb83  xor     ebx, ebx
0x18007cb85  mov     rcx, gs:60h
0x18007cb8e  mov     r8, [rsp+1C8h+NtName.Buffer]; P
0x18007cb93  xor     edx, edx; Flags
0x18007cb95  mov     rcx, [rcx+30h]; HeapHandle
0x18007cb99  call    cs:__imp_RtlFreeHeap
0x18007cb9f  cmp     [rsp+1C8h+var_C0], ebx
0x18007cba6  jl      short loc_18007CC27
0x18007cba8  jmp     short loc_18007CBAE
0x18007cbaa  jmp     short loc_18007CB83
0x18007cbac  jmp     short loc_18007CB83
0x18007cbae  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007cbb5  mov     [rsp+1C8h+var_C8], rax
0x18007cbbd  lea     rcx, [rsp+1C8h+var_C8]; this
0x18007cbc5  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007cbca  mov     rcx, [rsp+1C8h+var_18]
0x18007cbd2  xor     rcx, rsp; StackCookie
0x18007cbd5  call    __security_check_cookie
0x18007cbda  lea     r11, [rsp+1C8h+var_8]
0x18007cbe2  mov     rbx, [r11+20h]
0x18007cbe6  mov     rsi, [r11+28h]
0x18007cbea  mov     rsp, r11
0x18007cbed  pop     rdi
0x18007cbee  retn
0x18007cbef  mov     edx, 80045301h; int
0x18007cbf4  lea     rcx, [rsp+1C8h+var_C8]; this
0x18007cbfc  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18007cc01  lea     rcx, [rsp+1C8h+var_C8]; this
0x18007cc09  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18007cc0e  mov     r8d, eax; char
0x18007cc11  xor     r9d, r9d; unsigned __int16 *
0x18007cc14  mov     edx, 3D9h; unsigned int
0x18007cc19  lea     rcx, [rsp+1C8h+var_C8]; this
0x18007cc21  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18007cc27  lea     rcx, [rsp+1C8h+var_C8]; this
0x18007cc2f  call    ?ReThrow@CSrmFunctionTracer@@QEAAXXZ; CSrmFunctionTracer::ReThrow(void)
```
