# CSrmAutoPWSZ::Allocate(unsigned __int64)

- ea: `0x180005e50`
- end: `0x180005f99`
- name: `?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z`
- size: `329`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000be1c`

## callees

- `0x180005e50`
- `0x1800161e8`
- `0x18001623c`
- `0x180016564`
- `0x1800191ec`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005ef4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005ef4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005f06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005f06`

## pseudocode

```c
void __fastcall CSrmAutoPWSZ::Allocate(LPVOID *this)
{
  LPVOID v2; // rax
  __int64 v3; // rax
  _QWORD v4[3]; // [rsp+48h] [rbp-B8h] BYREF
  int v5; // [rsp+60h] [rbp-A0h]
  int v6; // [rsp+64h] [rbp-9Ch]
  int v7; // [rsp+68h] [rbp-98h]
  _BYTE v8[96]; // [rsp+70h] [rbp-90h] BYREF
  int v9; // [rsp+D0h] [rbp-30h]
  _BYTE v10[152]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v11[22]; // [rsp+170h] [rbp+70h] BYREF

  v4[0] = L"base\\fs\\fsrm\\utilities\\inc\\srmstr.h";
  v4[1] = L"CSrmAutoPWSZ::Allocate";
  v4[2] = L"INCLSTRH";
  v5 = 342;
  v6 = 17;
  v7 = 255;
  v9 = 0x1000000;
  memset_0(v8, 0, sizeof(v8));
  CSrmFunctionTracer::CSrmFunctionTracer(
    (__int64)v11,
    (const struct CSrmDebugInfo *)v4,
    (__int64)L"CSrmAutoPWSZ::Allocate");
  CoTaskMemFree(*this);
  *this = 0;
  v2 = CoTaskMemAlloc(0x7D2u);
  if ( !v2 )
  {
    v3 = CSrmDebugInfo::CSrmDebugInfo(
           (__int64)v10,
           (__int64)L"base\\fs\\fsrm\\utilities\\inc\\srmstr.h",
           (__int64)L"INCLSTRH",
           (__int64)L"SrmAllocString",
           141,
           17);
    CSrmFunctionTracer::Throw(v11, v3, 2147942414LL, L"Memory allocation error");
  }
  *this = v2;
  v11[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v11);
}

```

## disassembly

```asm
0x180005e50  mov     [rsp-8+arg_8], rbx
0x180005e55  mov     [rsp-8+arg_10], rsi
0x180005e5a  push    rbp
0x180005e5b  push    rdi
0x180005e5c  push    r14
0x180005e5e  lea     rbp, [rsp-130h]
0x180005e66  sub     rsp, 230h
0x180005e6d  mov     rax, cs:__security_cookie
0x180005e74  xor     rax, rsp
0x180005e77  mov     [rbp+140h+var_20], rax
0x180005e7e  mov     rbx, rcx
0x180005e81  lea     rax, [rsp+240h+var_1F8]
0x180005e86  mov     [rsp+240h+var_200], rax
0x180005e8b  lea     rsi, aBaseFsFsrmUtil_0; "base\\fs\\fsrm\\utilities\\inc\\srmstr."...
0x180005e92  mov     [rsp+240h+var_1F8], rsi
0x180005e97  lea     rdi, aCsrmautopwszAl; "CSrmAutoPWSZ::Allocate"
0x180005e9e  mov     [rsp+240h+var_1F0], rdi
0x180005ea3  lea     r14, aInclstrh; "INCLSTRH"
0x180005eaa  mov     [rsp+240h+var_1E8], r14
0x180005eaf  mov     [rsp+240h+var_1E0], 156h
0x180005eb7  mov     [rsp+240h+var_1DC], 11h
0x180005ebf  mov     [rsp+240h+var_1D8], 0FFh
0x180005ec7  mov     [rbp+140h+var_170], 1000000h
0x180005ece  xor     edx, edx; Val
0x180005ed0  lea     r8d, [rdx+60h]; Size
0x180005ed4  lea     rcx, [rsp+240h+var_1D0]; void *
0x180005ed9  call    memset_0
0x180005ede  nop
0x180005edf  mov     r8, rdi
0x180005ee2  lea     rdx, [rsp+240h+var_1F8]
0x180005ee7  lea     rcx, [rbp+140h+var_D0]
0x180005eeb  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180005ef0  nop
0x180005ef1  mov     rcx, [rbx]; pv
0x180005ef4  call    cs:__imp_CoTaskMemFree
0x180005efa  mov     qword ptr [rbx], 0
0x180005f01  mov     ecx, 7D2h; cb
0x180005f06  call    cs:__imp_CoTaskMemAlloc
0x180005f0c  test    rax, rax
0x180005f0f  jz      short loc_180005F4F
0x180005f11  mov     [rbx], rax
0x180005f14  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180005f1b  mov     [rbp+140h+var_D0], rax
0x180005f1f  lea     rcx, [rbp+140h+var_D0]; this
0x180005f23  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180005f28  mov     rcx, [rbp+140h+var_20]
0x180005f2f  xor     rcx, rsp; StackCookie
0x180005f32  call    __security_check_cookie
0x180005f37  lea     r11, [rsp+240h+var_10]
0x180005f3f  mov     rbx, [r11+28h]
0x180005f43  mov     rsi, [r11+30h]
0x180005f47  mov     rsp, r11
0x180005f4a  pop     r14
0x180005f4c  pop     rdi
0x180005f4d  pop     rbp
0x180005f4e  retn
0x180005f4f  lea     rax, [rbp+140h+var_168]
0x180005f53  mov     [rsp+240h+var_200], rax
0x180005f58  mov     [rsp+240h+var_218], 11h
0x180005f60  mov     [rsp+240h+var_220], 8Dh
0x180005f68  lea     r9, aSrmallocstring; "SrmAllocString"
0x180005f6f  mov     r8, r14
0x180005f72  mov     rdx, rsi
0x180005f75  lea     rcx, [rbp+140h+var_168]
0x180005f79  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180005f7e  nop
0x180005f7f  lea     r9, aMemoryAllocati; "Memory allocation error"
0x180005f86  mov     r8d, 8007000Eh
0x180005f8c  mov     rdx, rax
0x180005f8f  lea     rcx, [rbp+140h+var_D0]
0x180005f93  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```
