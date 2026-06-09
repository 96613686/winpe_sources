# OpenVolumeCheck(ushort const *,CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>> &)

- ea: `0x18007ef3c`
- end: `0x18007f14a`
- name: `?OpenVolumeCheck@@YAJPEBGAEAV?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@@Z`
- size: `526`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x18007fbd8`

## callees

- `0x18000af40`
- `0x18006febc`
- `0x1800700b8`
- `0x180074048`
- `0x18007ef3c`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18007f0f9`
- `ole32!CoTaskMemFree` at `0x18007f0f9`
- `KERNEL32!CreateFileW` at `0x18007f041`
- `KERNEL32!CreateFileW` at `0x18007f041`
- `KERNEL32!CloseHandle` at `0x18007f054`
- `KERNEL32!CloseHandle` at `0x18007f054`
- `KERNEL32!GetLastError` at `0x18007f05e`
- `KERNEL32!GetLastError` at `0x18007f05e`

## string_xrefs

- `0x18007f0de`: `Unable to open volume %s, %#x`
- `0x18007ef8a`: `OpenVolumeCheck`
- `0x18007f08f`: `OpenVolumeCheck`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OpenVolumeCheck(unsigned __int16 *a1, __int64 a2)
{
  unsigned __int16 *v4; // rbx
  __int64 v5; // rdi
  HANDLE FileW; // rdi
  void *v7; // rcx
  signed int LastError; // eax
  signed int v9; // edi
  unsigned int v10; // edi
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v13; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 **v14; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v15; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v16; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v17; // [rsp+60h] [rbp-A0h]
  int v18; // [rsp+68h] [rbp-98h]
  int v19; // [rsp+6Ch] [rbp-94h]
  int v20; // [rsp+70h] [rbp-90h]
  _BYTE v21[96]; // [rsp+78h] [rbp-88h] BYREF
  int v22; // [rsp+D8h] [rbp-28h]
  void **v23; // [rsp+E0h] [rbp-20h] BYREF
  signed int v24; // [rsp+E8h] [rbp-18h]

  v14 = &v15;
  v15 = L"base\\fs\\fsrm\\utilities\\volume\\srmvol.cpp";
  v16 = L"OpenVolumeCheck";
  v17 = L"SRMVOLMC";
  v18 = 621;
  v19 = 17;
  v20 = 255;
  v22 = 0x1000000;
  memset_0(v21, 0, sizeof(v21));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v23, (const struct CSrmDebugInfo *)&v15, 0);
  v4 = 0;
  v13 = 0;
  v5 = -1;
  do
    ++v5;
  while ( a1[v5] );
  if ( a1[v5 - 1] == 92 )
  {
    CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v13, a1);
    v4 = v13;
    a1 = v13;
    v13[v5 - 1] = 0;
  }
  FileW = CreateFileW(a1, 0x80u, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v7 = *(void **)(a2 + 8);
  if ( v7 != (void *)-1LL )
    CloseHandle(v7);
  *(_QWORD *)(a2 + 8) = FileW;
  LastError = GetLastError();
  v9 = LastError;
  if ( *(_QWORD *)(a2 + 8) == -1 )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v24 = LastError;
    v14 = &v15;
    v15 = L"base\\fs\\fsrm\\utilities\\volume\\srmvol.cpp";
    v16 = L"OpenVolumeCheck";
    v17 = L"SRMVOLMC";
    v18 = 654;
    v19 = 17;
    v20 = 255;
    v22 = 0x1000000;
    memset_0(v21, 0, sizeof(v21));
    LODWORD(dwCreationDisposition) = v9;
    CSrmFunctionTracer::Trace(&v23, &v15, L"Unable to open volume %s, %#x", a1, dwCreationDisposition);
  }
  v10 = v24;
  CoTaskMemFree(v4);
  v13 = 0;
  v23 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v23);
  return v10;
}

```

## disassembly

```asm
0x18007ef3c  mov     [rsp-8+arg_10], rbx
0x18007ef41  mov     [rsp-8+arg_18], rsi
0x18007ef46  push    rbp
0x18007ef47  push    rdi
0x18007ef48  push    r13
0x18007ef4a  push    r14
0x18007ef4c  push    r15
0x18007ef4e  lea     rbp, [rsp-0A0h]
0x18007ef56  sub     rsp, 1A0h
0x18007ef5d  mov     rax, cs:__security_cookie
0x18007ef64  xor     rax, rsp
0x18007ef67  mov     [rbp+0C0h+var_30], rax
0x18007ef6e  mov     r14, rdx
0x18007ef71  mov     rsi, rcx
0x18007ef74  lea     rax, [rsp+1C0h+var_170]
0x18007ef79  mov     [rsp+1C0h+var_178], rax
0x18007ef7e  lea     r13, aBaseFsFsrmUtil_2; "base\\fs\\fsrm\\utilities\\volume\\srmv"...
0x18007ef85  mov     [rsp+1C0h+var_170], r13
0x18007ef8a  lea     rax, aOpenvolumechec; "OpenVolumeCheck"
0x18007ef91  mov     [rsp+1C0h+var_168], rax
0x18007ef96  lea     rax, aSrmvolmc; "SRMVOLMC"
0x18007ef9d  mov     [rsp+1C0h+var_160], rax
0x18007efa2  mov     [rsp+1C0h+var_158], 26Dh
0x18007efaa  mov     [rsp+1C0h+var_154], 11h
0x18007efb2  mov     [rsp+1C0h+var_150], 0FFh
0x18007efba  xor     r15d, r15d
0x18007efbd  mov     [rbp+0C0h+var_E8], 1000000h
0x18007efc4  xor     edx, edx; Val
0x18007efc6  lea     r8d, [r15+60h]; Size
0x18007efca  lea     rcx, [rsp+1C0h+var_148]; void *
0x18007efcf  call    memset_0
0x18007efd4  nop
0x18007efd5  xor     r8d, r8d
0x18007efd8  lea     rdx, [rsp+1C0h+var_170]
0x18007efdd  lea     rcx, [rbp+0C0h+var_E0]
0x18007efe1  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007efe6  nop
0x18007efe7  mov     ebx, r15d
0x18007efea  mov     [rsp+1C0h+var_180], rbx
0x18007efef  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007eff3  inc     rdi
0x18007eff6  cmp     [rsi+rdi*2], r15w
0x18007effb  jnz     short loc_18007EFF3
0x18007effd  cmp     word ptr [rsi+rdi*2-2], 5Ch ; '\'
0x18007f003  jnz     short loc_18007F020
0x18007f005  mov     rdx, rsi; unsigned __int16 *
0x18007f008  lea     rcx, [rsp+1C0h+var_180]; this
0x18007f00d  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18007f012  mov     rbx, [rsp+1C0h+var_180]
0x18007f017  mov     rsi, rbx
0x18007f01a  mov     [rbx+rdi*2-2], r15w
0x18007f020  mov     [rsp+1C0h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x18007f029  mov     edx, 80h; dwDesiredAccess
0x18007f02e  mov     [rsp+1C0h+dwFlagsAndAttributes], edx; dwFlagsAndAttributes
0x18007f032  lea     r8d, [rdx-7Dh]; dwShareMode
0x18007f036  mov     dword ptr [rsp+1C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18007f03b  xor     r9d, r9d; lpSecurityAttributes
0x18007f03e  mov     rcx, rsi; lpFileName
0x18007f041  call    cs:__imp_CreateFileW
0x18007f047  mov     rdi, rax
0x18007f04a  mov     rcx, [r14+8]; hObject
0x18007f04e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18007f052  jz      short loc_18007F05A
0x18007f054  call    cs:__imp_CloseHandle
0x18007f05a  mov     [r14+8], rdi
0x18007f05e  call    cs:__imp_GetLastError
0x18007f064  mov     edi, eax
0x18007f066  cmp     qword ptr [r14+8], 0FFFFFFFFFFFFFFFFh
0x18007f06b  jnz     loc_18007F0F3
0x18007f071  test    eax, eax
0x18007f073  jle     short loc_18007F07D
0x18007f075  movzx   eax, di
0x18007f078  or      eax, 80070000h
0x18007f07d  mov     [rbp+0C0h+var_D8], eax
0x18007f080  lea     rax, [rsp+1C0h+var_170]
0x18007f085  mov     [rsp+1C0h+var_178], rax
0x18007f08a  mov     [rsp+1C0h+var_170], r13
0x18007f08f  lea     rax, aOpenvolumechec; "OpenVolumeCheck"
0x18007f096  mov     [rsp+1C0h+var_168], rax
0x18007f09b  lea     rax, aSrmvolmc; "SRMVOLMC"
0x18007f0a2  mov     [rsp+1C0h+var_160], rax
0x18007f0a7  mov     [rsp+1C0h+var_158], 28Eh
0x18007f0af  mov     [rsp+1C0h+var_154], 11h
0x18007f0b7  mov     [rsp+1C0h+var_150], 0FFh
0x18007f0bf  mov     [rbp+0C0h+var_E8], 1000000h
0x18007f0c6  xor     edx, edx; Val
0x18007f0c8  lea     r8d, [rdx+60h]; Size
0x18007f0cc  lea     rcx, [rsp+1C0h+var_148]; void *
0x18007f0d1  call    memset_0
0x18007f0d6  nop
0x18007f0d7  mov     dword ptr [rsp+1C0h+dwCreationDisposition], edi
0x18007f0db  mov     r9, rsi
0x18007f0de  lea     r8, aUnableToOpenVo; "Unable to open volume %s, %#x"
0x18007f0e5  lea     rdx, [rsp+1C0h+var_170]
0x18007f0ea  lea     rcx, [rbp+0C0h+var_E0]
0x18007f0ee  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18007f0f3  mov     edi, [rbp+0C0h+var_D8]
0x18007f0f6  mov     rcx, rbx; pv
0x18007f0f9  call    cs:__imp_CoTaskMemFree
0x18007f0ff  mov     [rsp+1C0h+var_180], r15
0x18007f104  mov     [rsp+1C0h+var_180], r15
0x18007f109  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007f110  mov     [rbp+0C0h+var_E0], rax
0x18007f114  lea     rcx, [rbp+0C0h+var_E0]; this
0x18007f118  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007f11d  mov     eax, edi
0x18007f11f  mov     rcx, [rbp+0C0h+var_30]
0x18007f126  xor     rcx, rsp; StackCookie
0x18007f129  call    __security_check_cookie
0x18007f12e  lea     r11, [rsp+1C0h+var_20]
0x18007f136  mov     rbx, [r11+40h]
0x18007f13a  mov     rsi, [r11+48h]
0x18007f13e  mov     rsp, r11
0x18007f141  pop     r15
0x18007f143  pop     r14
0x18007f145  pop     r13
0x18007f147  pop     rdi
0x18007f148  pop     rbp
0x18007f149  retn
```
