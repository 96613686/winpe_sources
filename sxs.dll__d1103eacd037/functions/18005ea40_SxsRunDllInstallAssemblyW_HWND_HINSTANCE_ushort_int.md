# SxsRunDllInstallAssemblyW(HWND__ *,HINSTANCE__ *,ushort *,int)

- ea: `0x18005ea40`
- end: `0x18005eb7b`
- name: `?SxsRunDllInstallAssemblyW@@YAXPEAUHWND__@@PEAUHINSTANCE__@@PEAGH@Z`
- size: `315`
- prototype: `void(HWND, HINSTANCE, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18005e960`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18001e5d0`
- `0x180020820`
- `0x18004d370`
- `0x18005ea40`
- `0x18005f1f0`
- `0x18005fd00`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ead6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ead6`

## string_xrefs

- `0x18005eb24`: `RunDll32`

## pseudocode

```c
void __fastcall SxsRunDllInstallAssemblyW(HWND a1, HINSTANCE a2, unsigned __int16 *a3)
{
  __int64 v4; // rdx
  _QWORD v5[5]; // [rsp+20h] [rbp-E0h] BYREF
  int v6; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v7; // [rsp+4Ch] [rbp-B4h]
  __int128 v8; // [rsp+5Ch] [rbp-A4h]
  _BYTE v9[20]; // [rsp+6Ch] [rbp-94h] BYREF
  int v10; // [rsp+80h] [rbp-80h] BYREF
  __int64 v11; // [rsp+88h] [rbp-78h]
  __int64 *v12; // [rsp+90h] [rbp-70h]
  __int64 v13; // [rsp+98h] [rbp-68h]
  int v14; // [rsp+A0h] [rbp-60h]
  _BYTE v15[16]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v16; // [rsp+C0h] [rbp-40h]

  v10 = 1;
  v12 = &qword_1800747B0;
  v11 = 0;
  v13 = 544438355;
  v14 = 449;
  CFrame::BaseEnter((CFrame *)&v10);
  v6 = 56;
  LODWORD(v5[0]) = 40;
  v7 = 0;
  v8 = 0;
  memset(v9, 0, sizeof(v9));
  memset((char *)v5 + 4, 0, 36);
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v15);
  SetLastError(0);
  if ( (unsigned int)SxspExpandRelativePathToFull(a3, v4, (__int64)v15) )
  {
    *(_QWORD *)((char *)&v7 + 4) = v16;
    *(_QWORD *)((char *)&v8 + 4) = v16;
    *(_QWORD *)&v9[12] = v5;
    v5[3] = L"RunDll32";
    LODWORD(v7) = 2130176;
    HIDWORD(v5[0]) = 0;
    *(_OWORD *)&v5[1] = SXS_INSTALL_REFERENCE_SCHEME_OPAQUESTRING;
    SxsInstallW(&v6);
  }
  else
  {
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180074790);
  }
  CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(v15);
  CFnTracer::~CFnTracer((CFnTracer *)&v10);
}

```

## disassembly

```asm
0x18005ea40  mov     [rsp-8+arg_0], rbx
0x18005ea45  push    rbp
0x18005ea46  lea     rbp, [rsp-70h]
0x18005ea4b  sub     rsp, 170h
0x18005ea52  mov     rax, cs:__security_cookie
0x18005ea59  xor     rax, rsp
0x18005ea5c  mov     [rbp+70h+var_10], rax
0x18005ea60  lea     rax, qword_1800747B0
0x18005ea67  mov     [rbp+70h+var_F0], 1
0x18005ea6e  lea     rcx, [rbp+70h+var_F0]; this
0x18005ea72  mov     [rbp+70h+var_E0], rax
0x18005ea76  mov     rbx, r8
0x18005ea79  mov     [rbp+70h+var_E8], 0
0x18005ea81  mov     [rbp+70h+var_D8], 20737853h
0x18005ea89  mov     [rbp+70h+var_D0], 1C1h
0x18005ea90  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18005ea95  xorps   xmm0, xmm0
0x18005ea98  mov     [rsp+170h+var_128], 38h ; '8'
0x18005eaa0  xor     eax, eax
0x18005eaa2  mov     [rsp+170h+var_150], 28h ; '('
0x18005eaaa  lea     rcx, [rbp+70h+var_C0]
0x18005eaae  mov     [rsp+170h+var_F4], eax
0x18005eab2  movups  [rsp+170h+var_124], xmm0
0x18005eab7  mov     [rsp+170h+var_12C], eax
0x18005eabb  movups  [rsp+170h+var_114], xmm0
0x18005eac0  movups  [rsp+170h+var_104], xmm0
0x18005eac5  movups  [rsp+170h+var_14C], xmm0
0x18005eaca  movups  [rsp+170h+var_13C], xmm0
0x18005eacf  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18005ead4  xor     ecx, ecx; dwErrCode
0x18005ead6  call    cs:__imp_SetLastError
0x18005eadd  nop     dword ptr [rax+rax+00h]
0x18005eae2  lea     r8, [rbp+70h+var_C0]
0x18005eae6  mov     rcx, rbx; lpFileName
0x18005eae9  call    ?SxspExpandRelativePathToFull@@YAHPEBG_KAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; SxspExpandRelativePathToFull(ushort const *,unsigned __int64,CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x18005eaee  test    eax, eax
0x18005eaf0  jnz     short loc_18005EB00
0x18005eaf2  lea     rcx, off_180074790; struct _CALL_SITE_INFO *
0x18005eaf9  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18005eafe  jmp     short loc_18005EB4B
0x18005eb00  mov     rax, [rbp+70h+var_B0]
0x18005eb04  lea     rcx, [rsp+170h+var_128]
0x18005eb09  movups  xmm0, cs:SXS_INSTALL_REFERENCE_SCHEME_OPAQUESTRING
0x18005eb10  mov     qword ptr [rsp+170h+var_124+4], rax
0x18005eb15  mov     qword ptr [rsp+170h+var_114+4], rax
0x18005eb1a  lea     rax, [rsp+170h+var_150]
0x18005eb1f  mov     qword ptr [rsp+170h+var_104+0Ch], rax
0x18005eb24  lea     rax, aRundll32; "RunDll32"
0x18005eb2b  mov     qword ptr [rsp+170h+var_13C+4], rax
0x18005eb30  mov     dword ptr [rsp+170h+var_124], 208100h
0x18005eb38  mov     dword ptr [rsp+170h+var_14C], 0
0x18005eb40  movdqu  [rsp+170h+var_14C+4], xmm0
0x18005eb46  call    SxsInstallW
0x18005eb4b  lea     rcx, [rbp+70h+var_C0]
0x18005eb4f  call    ??1?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18005eb54  lea     rcx, [rbp+70h+var_F0]; this
0x18005eb58  call    ??1CFnTracer@@QEAA@XZ; CFnTracer::~CFnTracer(void)
0x18005eb5d  mov     rcx, [rbp+70h+var_10]
0x18005eb61  xor     rcx, rsp; StackCookie
0x18005eb64  call    __security_check_cookie
0x18005eb69  mov     rbx, [rsp+170h+arg_0]
0x18005eb71  add     rsp, 170h
0x18005eb78  pop     rbp
0x18005eb79  retn
```
