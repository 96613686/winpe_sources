# SrmIsPathDirectoryJunction(ushort const *)

- ea: `0x18007d4c4`
- end: `0x18007d90b`
- name: `?SrmIsPathDirectoryJunction@@YA_NPEBG@Z`
- size: `1095`
- prototype: `bool __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, service_task`

## callers

- `0x18007b5f4`

## callees

- `0x180006a1c`
- `0x18000ad14`
- `0x18000c7f8`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180074a04`
- `0x18007afe4`
- `0x18007d4c4`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18007d788`
- `ole32!CoTaskMemFree` at `0x18007d788`
- `KERNEL32!CreateFileW` at `0x18007d5b0`
- `KERNEL32!CreateFileW` at `0x18007d5b0`
- `KERNEL32!CloseHandle` at `0x18007d7d7`
- `KERNEL32!CloseHandle` at `0x18007d840`
- `KERNEL32!CloseHandle` at `0x18007d7d7`
- `KERNEL32!CloseHandle` at `0x18007d840`
- `KERNEL32!LocalFree` at `0x18007d7ac`
- `KERNEL32!LocalFree` at `0x18007d81c`
- `KERNEL32!LocalFree` at `0x18007d7ac`
- `KERNEL32!LocalFree` at `0x18007d81c`
- `KERNEL32!DeviceIoControl` at `0x18007d664`
- `KERNEL32!DeviceIoControl` at `0x18007d664`

## string_xrefs

- `0x18007d8f4`: `StringCchCopy`
- `0x18007d4fe`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007d8e2`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007d515`: `SRMPATHC`
- `0x18007d8db`: `SRMPATHC`
- `0x18007d50a`: `SrmIsPathDirectoryJunction`
- `0x18007d8d4`: `SrmIsPathDirectoryJunction`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
char __fastcall SrmIsPathDirectoryJunction(LPCWSTR lpFileName)
{
  char v2; // r14
  HANDLE FileW; // rdi
  unsigned __int16 *v4; // rbx
  unsigned __int64 v5; // rsi
  _WORD *v6; // r11
  unsigned int Hr; // ebx
  __int64 v9; // rax
  void **v10; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID lpOutBuffer; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v12; // [rsp+60h] [rbp-A0h] BYREF
  DWORD BytesReturned; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v14; // [rsp+70h] [rbp-90h]
  _QWORD v15[4]; // [rsp+78h] [rbp-88h] BYREF
  int v16; // [rsp+98h] [rbp-68h]
  _BYTE v17[96]; // [rsp+A0h] [rbp-60h] BYREF
  int v18; // [rsp+100h] [rbp+0h]
  void **v19; // [rsp+110h] [rbp+10h] BYREF
  int v20; // [rsp+118h] [rbp+18h]

  v12 = (unsigned __int16 *)v15;
  v15[0] = L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp";
  v15[1] = L"SrmIsPathDirectoryJunction";
  v15[2] = L"SRMPATHC";
  v15[3] = 627;
  v16 = 255;
  v18 = 0x1000000;
  v2 = 1;
  memset_0(v17, 0, sizeof(v17));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v19, (const struct CSrmDebugInfo *)v15, 0);
  if ( !lpFileName || !*lpFileName )
  {
    v19 = &CSrmFunctionTracer::`vftable';
    goto LABEL_38;
  }
  FileW = CreateFileW(lpFileName, 0, 3u, 0, 3u, 0x2200080u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( FileW == (HANDLE)-1LL )
  {
    v19 = &CSrmFunctionTracer::`vftable';
LABEL_38:
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v19);
    return 0;
  }
  lpOutBuffer = 0;
  v10 = &CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable';
  BytesReturned = 0;
  CSrmAutoLocalPtr_Storage<_REPARSE_DATA_BUFFER *>::AllocateBytes(&v10);
  v4 = (unsigned __int16 *)lpOutBuffer;
  if ( !DeviceIoControl(FileW, 0x900A8u, 0, 0, lpOutBuffer, 0x4000u, &BytesReturned, 0) || *(_DWORD *)v4 != -1610612733 )
  {
    v10 = &CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable';
    if ( v4 )
      LocalFree(v4);
    v10 = &CSrmAutoLocalPtr_Storage<void *>::`vftable';
    lpOutBuffer = 0;
    CloseHandle(FileW);
    v19 = &CSrmFunctionTracer::`vftable';
    goto LABEL_38;
  }
  v12 = 0;
  v5 = v4[5];
  CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&v12, v5);
  v20 = StringCchCopyW(v12, v5 + 1, &v4[v4[4] + 8]);
  if ( v20 < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v19);
    v14 = v15;
    v9 = CSrmDebugInfo::CSrmDebugInfo(
           (__int64)v15,
           (__int64)L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp",
           (__int64)L"SRMPATHC",
           (__int64)L"SrmIsPathDirectoryJunction",
           693,
           17);
    CSrmFunctionTracer::TranslateGenericError(&v19, v9, Hr, L"StringCchCopy");
  }
  v6[1] = 92;
  *(_WORD *)((char *)v6 + (v4[5] & 0xFFFE)) = 0;
  if ( ((_WORD)v5 == 96 || (_DWORD)v5 == 98 && v6[48] == 92)
    && *v6 == 92
    && (v6[1] == 63 || v6[1] == 92)
    && v6[2] == 63
    && v6[3] == 92
    && v6[4] == 86
    && v6[5] == 111
    && v6[6] == 108
    && v6[7] == 117
    && v6[8] == 109
    && v6[9] == 101
    && v6[10] == 123
    && v6[19] == 45
    && v6[24] == 45
    && v6[29] == 45
    && v6[34] == 45
    && v6[47] == 125
    && (_DWORD)v5 == 98
    && v6[1] == 92 )
  {
    v2 = 0;
  }
  CoTaskMemFree(v6);
  v12 = 0;
  v10 = &CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable';
  if ( v4 )
    LocalFree(v4);
  v10 = &CSrmAutoLocalPtr_Storage<void *>::`vftable';
  lpOutBuffer = 0;
  CloseHandle(FileW);
  v19 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v19);
  return v2;
}

```

## disassembly

```asm
0x18007d4c4  push    rbp
0x18007d4c6  push    rbx
0x18007d4c7  push    rsi
0x18007d4c8  push    rdi
0x18007d4c9  push    r12
0x18007d4cb  push    r13
0x18007d4cd  push    r14
0x18007d4cf  push    r15
0x18007d4d1  lea     rbp, [rsp-0D8h]
0x18007d4d9  sub     rsp, 1D8h
0x18007d4e0  mov     rax, cs:__security_cookie
0x18007d4e7  xor     rax, rsp
0x18007d4ea  mov     [rbp+110h+var_50], rax
0x18007d4f1  mov     rbx, rcx
0x18007d4f4  lea     rax, [rsp+210h+var_198]
0x18007d4f9  mov     [rsp+210h+var_1B0], rax
0x18007d4fe  lea     rax, aBaseFsFsrmUtil_6; "base\\fs\\fsrm\\utilities\\path\\srmpat"...
0x18007d505  mov     [rsp+210h+var_198], rax
0x18007d50a  lea     rax, aSrmispathdirec; "SrmIsPathDirectoryJunction"
0x18007d511  mov     [rbp+110h+var_190], rax
0x18007d515  lea     rax, aSrmpathc; "SRMPATHC"
0x18007d51c  mov     [rbp+110h+var_188], rax
0x18007d520  mov     [rbp+110h+var_180], 273h
0x18007d528  xor     r15d, r15d
0x18007d52b  mov     [rbp+110h+var_178], 0FFh
0x18007d532  mov     [rbp+110h+var_110], 1000000h
0x18007d539  mov     r14b, 1
0x18007d53c  xor     edx, edx; Val
0x18007d53e  lea     r8d, [r15+60h]; Size
0x18007d542  lea     rcx, [rbp+110h+var_170]; void *
0x18007d546  call    memset_0
0x18007d54b  nop
0x18007d54c  xor     r8d, r8d
0x18007d54f  lea     rdx, [rsp+210h+var_198]
0x18007d554  lea     rcx, [rbp+110h+var_100]
0x18007d558  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007d55d  nop
0x18007d55e  lea     r13, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18007d565  mov     [rsp+210h+var_1D0], r13
0x18007d56a  or      r12, 0FFFFFFFFFFFFFFFFh
0x18007d56e  mov     [rsp+210h+var_1C8], r12
0x18007d573  lea     rsi, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18007d57a  mov     [rsp+210h+var_1D0], rsi
0x18007d57f  test    rbx, rbx
0x18007d582  jz      loc_18007D862
0x18007d588  cmp     [rbx], r15w
0x18007d58c  jz      loc_18007D862
0x18007d592  mov     [rsp+210h+hTemplateFile], r12; hTemplateFile
0x18007d597  mov     [rsp+210h+dwFlagsAndAttributes], 2200080h; dwFlagsAndAttributes
0x18007d59f  lea     r8d, [r15+3]; dwShareMode
0x18007d5a3  mov     [rsp+210h+dwCreationDisposition], r8d; dwCreationDisposition
0x18007d5a8  xor     r9d, r9d; lpSecurityAttributes
0x18007d5ab  xor     edx, edx; dwDesiredAccess
0x18007d5ad  mov     rcx, rbx; lpFileName
0x18007d5b0  call    cs:__imp_CreateFileW
0x18007d5b6  mov     rdi, rax
0x18007d5b9  mov     [rsp+210h+var_1C8], r12
0x18007d5be  mov     [rsp+210h+var_1C8], rax
0x18007d5c3  cmp     rax, r12
0x18007d5c6  jnz     short loc_18007D5EC
0x18007d5c8  mov     [rsp+210h+var_1D0], rsi
0x18007d5cd  mov     [rsp+210h+var_1C8], r12
0x18007d5d2  mov     [rsp+210h+var_1D0], r13
0x18007d5d7  mov     [rsp+210h+var_1C8], r12
0x18007d5dc  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007d5e3  mov     [rbp+110h+var_100], rax
0x18007d5e7  jmp     loc_18007D881
0x18007d5ec  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x18007d5f3  mov     [rsp+210h+var_1C0], rax
0x18007d5f8  mov     [rsp+210h+lpOutBuffer], r15
0x18007d5fd  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAE@@6B@; const CSrmAutoLocalPtr_Storage<uchar *>::`vftable'
0x18007d604  mov     [rsp+210h+var_1C0], rax
0x18007d609  lea     rax, ??_7?$CSrmAuto@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@V?$CSrmAutoLocalPtr_Storage@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@@@6B@; const CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable'
0x18007d610  mov     [rsp+210h+var_1C0], rax
0x18007d615  mov     [rsp+210h+lpOutBuffer], r15
0x18007d61a  lea     rax, ??_7?$CSrmAutoLocalPtr@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@6B@; const CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable'
0x18007d621  mov     [rsp+210h+var_1C0], rax
0x18007d626  mov     [rsp+210h+BytesReturned], r15d
0x18007d62b  lea     rcx, [rsp+210h+var_1C0]
0x18007d630  call    ?AllocateBytes@?$CSrmAutoLocalPtr_Storage@PEAU_REPARSE_DATA_BUFFER@@@@QEAAX_K@Z; CSrmAutoLocalPtr_Storage<_REPARSE_DATA_BUFFER *>::AllocateBytes(unsigned __int64)
0x18007d635  mov     rbx, [rsp+210h+lpOutBuffer]
0x18007d63a  mov     [rsp+210h+lpOverlapped], r15; lpOverlapped
0x18007d63f  lea     rax, [rsp+210h+BytesReturned]
0x18007d644  mov     [rsp+210h+hTemplateFile], rax; lpBytesReturned
0x18007d649  mov     [rsp+210h+dwFlagsAndAttributes], 4000h; nOutBufferSize
0x18007d651  mov     qword ptr [rsp+210h+dwCreationDisposition], rbx; lpOutBuffer
0x18007d656  xor     r9d, r9d; nInBufferSize
0x18007d659  xor     r8d, r8d; lpInBuffer
0x18007d65c  mov     edx, 900A8h; dwIoControlCode
0x18007d661  mov     rcx, rdi; hDevice
0x18007d664  call    cs:__imp_DeviceIoControl
0x18007d66a  test    eax, eax
0x18007d66c  jz      loc_18007D808
0x18007d672  cmp     dword ptr [rbx], 0A0000003h
0x18007d678  jnz     loc_18007D808
0x18007d67e  mov     [rsp+210h+var_1B0], r15
0x18007d683  movzx   esi, word ptr [rbx+0Ah]
0x18007d687  mov     edx, esi; unsigned __int64
0x18007d689  lea     rcx, [rsp+210h+var_1B0]; this
0x18007d68e  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x18007d693  movzx   eax, word ptr [rbx+8]
0x18007d697  add     rax, 8
0x18007d69b  lea     r8, [rbx+rax*2]; unsigned __int16 *
0x18007d69f  lea     rdx, [rsi+1]; unsigned __int64
0x18007d6a3  mov     r11, [rsp+210h+var_1B0]
0x18007d6a8  mov     rcx, r11; unsigned __int16 *
0x18007d6ab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007d6b0  mov     [rbp+110h+var_F8], eax
0x18007d6b3  test    eax, eax
0x18007d6b5  js      loc_18007D8AF
0x18007d6bb  mov     edx, 5Ch ; '\'
0x18007d6c0  mov     [r11+2], dx
0x18007d6c5  movzx   ecx, word ptr [rbx+0Ah]
0x18007d6c9  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18007d6cd  mov     [rcx+r11], r15w
0x18007d6d2  lea     eax, [rdx+4]
0x18007d6d5  cmp     si, ax
0x18007d6d8  jz      short loc_18007D6EE
0x18007d6da  cmp     esi, 62h ; 'b'
0x18007d6dd  jnz     loc_18007D785
0x18007d6e3  cmp     [r11+60h], dx
0x18007d6e8  jnz     loc_18007D785
0x18007d6ee  cmp     [r11], dx
0x18007d6f2  jnz     loc_18007D785
0x18007d6f8  cmp     word ptr [r11+2], 3Fh ; '?'
0x18007d6fe  jz      short loc_18007D707
0x18007d700  cmp     [r11+2], dx
0x18007d705  jnz     short loc_18007D785
0x18007d707  cmp     word ptr [r11+4], 3Fh ; '?'
0x18007d70d  jnz     short loc_18007D785
0x18007d70f  cmp     [r11+6], dx
0x18007d714  jnz     short loc_18007D785
0x18007d716  cmp     word ptr [r11+8], 56h ; 'V'
0x18007d71c  jnz     short loc_18007D785
0x18007d71e  cmp     word ptr [r11+0Ah], 6Fh ; 'o'
0x18007d724  jnz     short loc_18007D785
0x18007d726  cmp     word ptr [r11+0Ch], 6Ch ; 'l'
0x18007d72c  jnz     short loc_18007D785
0x18007d72e  cmp     word ptr [r11+0Eh], 75h ; 'u'
0x18007d734  jnz     short loc_18007D785
0x18007d736  cmp     word ptr [r11+10h], 6Dh ; 'm'
0x18007d73c  jnz     short loc_18007D785
0x18007d73e  cmp     word ptr [r11+12h], 65h ; 'e'
0x18007d744  jnz     short loc_18007D785
0x18007d746  cmp     word ptr [r11+14h], 7Bh ; '{'
0x18007d74c  jnz     short loc_18007D785
0x18007d74e  mov     ax, 2Dh ; '-'
0x18007d752  cmp     [r11+26h], ax
0x18007d757  jnz     short loc_18007D785
0x18007d759  cmp     [r11+30h], ax
0x18007d75e  jnz     short loc_18007D785
0x18007d760  cmp     [r11+3Ah], ax
0x18007d765  jnz     short loc_18007D785
0x18007d767  cmp     [r11+44h], ax
0x18007d76c  jnz     short loc_18007D785
0x18007d76e  cmp     word ptr [r11+5Eh], 7Dh ; '}'
0x18007d774  jnz     short loc_18007D785
0x18007d776  cmp     esi, 62h ; 'b'
0x18007d779  jnz     short loc_18007D785
0x18007d77b  cmp     [r11+2], dx
0x18007d780  jnz     short loc_18007D785
0x18007d782  mov     r14b, r15b
0x18007d785  mov     rcx, r11; pv
0x18007d788  call    cs:__imp_CoTaskMemFree
0x18007d78e  mov     [rsp+210h+var_1B0], r15
0x18007d793  mov     [rsp+210h+var_1B0], r15
0x18007d798  lea     rax, ??_7?$CSrmAuto@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@V?$CSrmAutoLocalPtr_Storage@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@@@6B@; const CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable'
0x18007d79f  mov     [rsp+210h+var_1C0], rax
0x18007d7a4  test    rbx, rbx
0x18007d7a7  jz      short loc_18007D7B2
0x18007d7a9  mov     rcx, rbx; hMem
0x18007d7ac  call    cs:__imp_LocalFree
0x18007d7b2  mov     [rsp+210h+lpOutBuffer], r15
0x18007d7b7  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x18007d7be  mov     [rsp+210h+var_1C0], rax
0x18007d7c3  mov     [rsp+210h+lpOutBuffer], r15
0x18007d7c8  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18007d7cf  mov     [rsp+210h+var_1D0], rax
0x18007d7d4  mov     rcx, rdi; hObject
0x18007d7d7  call    cs:__imp_CloseHandle
0x18007d7dd  mov     [rsp+210h+var_1C8], r12
0x18007d7e2  mov     [rsp+210h+var_1D0], r13
0x18007d7e7  mov     [rsp+210h+var_1C8], r12
0x18007d7ec  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007d7f3  mov     [rbp+110h+var_100], rax
0x18007d7f7  lea     rcx, [rbp+110h+var_100]; this
0x18007d7fb  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007d800  mov     al, r14b
0x18007d803  jmp     loc_18007D88C
0x18007d808  lea     rax, ??_7?$CSrmAuto@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@V?$CSrmAutoLocalPtr_Storage@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@@@6B@; const CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable'
0x18007d80f  mov     [rsp+210h+var_1C0], rax
0x18007d814  test    rbx, rbx
0x18007d817  jz      short loc_18007D822
0x18007d819  mov     rcx, rbx; hMem
0x18007d81c  call    cs:__imp_LocalFree
0x18007d822  mov     [rsp+210h+lpOutBuffer], r15
0x18007d827  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x18007d82e  mov     [rsp+210h+var_1C0], rax
0x18007d833  mov     [rsp+210h+lpOutBuffer], r15
0x18007d838  mov     [rsp+210h+var_1D0], rsi
0x18007d83d  mov     rcx, rdi; hObject
0x18007d840  call    cs:__imp_CloseHandle
0x18007d846  mov     [rsp+210h+var_1C8], r12
0x18007d84b  mov     [rsp+210h+var_1D0], r13
0x18007d850  mov     [rsp+210h+var_1C8], r12
0x18007d855  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007d85c  mov     [rbp+110h+var_100], rax
0x18007d860  jmp     short loc_18007D881
0x18007d862  mov     [rsp+210h+var_1D0], rsi
0x18007d867  mov     [rsp+210h+var_1C8], r12
0x18007d86c  mov     [rsp+210h+var_1D0], r13
0x18007d871  mov     [rsp+210h+var_1C8], r12
0x18007d876  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007d87d  mov     [rbp+110h+var_100], rax
0x18007d881  lea     rcx, [rbp+110h+var_100]; this
0x18007d885  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007d88a  xor     al, al
0x18007d88c  mov     rcx, [rbp+110h+var_50]
0x18007d893  xor     rcx, rsp; StackCookie
0x18007d896  call    __security_check_cookie
0x18007d89b  add     rsp, 1D8h
0x18007d8a2  pop     r15
0x18007d8a4  pop     r14
0x18007d8a6  pop     r13
0x18007d8a8  pop     r12
0x18007d8aa  pop     rdi
0x18007d8ab  pop     rsi
0x18007d8ac  pop     rbx
0x18007d8ad  pop     rbp
0x18007d8ae  retn
0x18007d8af  lea     rcx, [rbp+110h+var_100]; this
0x18007d8b3  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18007d8b8  mov     ebx, eax
0x18007d8ba  lea     rax, [rsp+210h+var_198]
0x18007d8bf  mov     [rsp+210h+var_1A0], rax
0x18007d8c4  mov     [rsp+210h+dwFlagsAndAttributes], 11h
0x18007d8cc  mov     [rsp+210h+dwCreationDisposition], 2B5h
0x18007d8d4  lea     r9, aSrmispathdirec; "SrmIsPathDirectoryJunction"
0x18007d8db  lea     r8, aSrmpathc; "SRMPATHC"
0x18007d8e2  lea     rdx, aBaseFsFsrmUtil_6; "base\\fs\\fsrm\\utilities\\path\\srmpat"...
0x18007d8e9  lea     rcx, [rsp+210h+var_198]
0x18007d8ee  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007d8f3  nop
0x18007d8f4  lea     r9, aStringcchcopy; "StringCchCopy"
0x18007d8fb  mov     r8d, ebx
0x18007d8fe  mov     rdx, rax
0x18007d901  lea     rcx, [rbp+110h+var_100]
0x18007d905  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
```
