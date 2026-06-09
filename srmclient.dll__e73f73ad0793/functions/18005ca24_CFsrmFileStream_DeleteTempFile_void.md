# CFsrmFileStream::DeleteTempFile(void)

- ea: `0x18005ca24`
- end: `0x18005cb68`
- name: `?DeleteTempFile@CFsrmFileStream@@AEAAXXZ`
- size: `324`
- prototype: `void __fastcall(CFsrmFileStream *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x18005af68`

## callees

- `0x18005ca24`
- `0x18006febc`
- `0x1800700b8`
- `0x180073f54`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005cada`
- `KERNEL32!GetLastError` at `0x18005cada`
- `KERNEL32!DeleteFileW` at `0x18005cad0`
- `KERNEL32!DeleteFileW` at `0x18005cad0`

## string_xrefs

- `0x18005ca57`: `base\fs\fsrm\service\inc\streamlib.h`
- `0x18005cafd`: `Cannot delete temp copy '%s', error %ld`
- `0x18005ca63`: `CFsrmFileStream::DeleteTempFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CFsrmFileStream::DeleteTempFile(CFsrmFileStream *this)
{
  const WCHAR *v2; // rbx
  const WCHAR *v3; // rcx
  DWORD LastError; // eax
  const WCHAR *v5; // rcx
  const WCHAR *v6; // rcx
  DWORD v7; // [rsp+28h] [rbp-D8h]
  _QWORD v8[3]; // [rsp+38h] [rbp-C8h] BYREF
  int v9; // [rsp+50h] [rbp-B0h]
  int v10; // [rsp+54h] [rbp-ACh]
  int v11; // [rsp+58h] [rbp-A8h]
  char v12[96]; // [rsp+60h] [rbp-A0h] BYREF
  int v13; // [rsp+C0h] [rbp-40h]
  _QWORD v14[22]; // [rsp+D0h] [rbp-30h] BYREF

  v8[0] = L"base\\fs\\fsrm\\service\\inc\\streamlib.h";
  v8[1] = L"CFsrmFileStream::DeleteTempFile";
  v8[2] = L"STREAMLH";
  v9 = 275;
  v10 = 17;
  v11 = 255;
  v13 = 0x1000000;
  memset_0(v12, 0, sizeof(v12));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v14, (const struct CSrmDebugInfo *)v8, 0);
  v2 = (const WCHAR *)((char *)this + 48);
  if ( *((_QWORD *)v2 + 3) < 8u )
    v3 = v2;
  else
    v3 = *(const WCHAR **)v2;
  if ( !DeleteFileW(v3) )
  {
    LastError = GetLastError();
    if ( LastError != 2 )
    {
      if ( *((_QWORD *)v2 + 3) < 8u )
        v5 = v2;
      else
        v5 = *(const WCHAR **)v2;
      v7 = LastError;
      CSrmFunctionTracer::Trace(
        (CSrmFunctionTracer *)v14,
        0x3Cu,
        0x120u,
        L"Cannot delete temp copy '%s', error %ld",
        v5,
        v7,
        v8);
    }
  }
  if ( *((_QWORD *)v2 + 3) < 8u )
    v6 = v2;
  else
    v6 = *(const WCHAR **)v2;
  *((_QWORD *)v2 + 2) = 0;
  *v6 = 0;
  v14[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v14);
}

```

## disassembly

```asm
0x18005ca24  mov     [rsp-8+arg_8], rbx
0x18005ca29  push    rbp
0x18005ca2a  lea     rbp, [rsp-90h]
0x18005ca32  sub     rsp, 190h
0x18005ca39  mov     rax, cs:__security_cookie
0x18005ca40  xor     rax, rsp
0x18005ca43  mov     [rbp+90h+var_10], rax
0x18005ca4a  mov     rbx, rcx
0x18005ca4d  lea     rax, [rsp+190h+var_158]
0x18005ca52  mov     [rsp+190h+var_160], rax
0x18005ca57  lea     rax, aBaseFsFsrmServ_32; "base\\fs\\fsrm\\service\\inc\\streamlib"...
0x18005ca5e  mov     [rsp+190h+var_158], rax
0x18005ca63  lea     rax, aCfsrmfilestrea_11; "CFsrmFileStream::DeleteTempFile"
0x18005ca6a  mov     [rsp+190h+var_150], rax
0x18005ca6f  lea     rax, aStreamlh; "STREAMLH"
0x18005ca76  mov     [rsp+190h+var_148], rax
0x18005ca7b  mov     [rsp+190h+var_140], 113h
0x18005ca83  mov     [rsp+190h+var_13C], 11h
0x18005ca8b  mov     [rsp+190h+var_138], 0FFh
0x18005ca93  mov     [rbp+90h+var_D0], 1000000h
0x18005ca9a  xor     edx, edx; Val
0x18005ca9c  lea     r8d, [rdx+60h]; Size
0x18005caa0  lea     rcx, [rsp+190h+var_130]; void *
0x18005caa5  call    memset_0
0x18005caaa  nop
0x18005caab  xor     r8d, r8d
0x18005caae  lea     rdx, [rsp+190h+var_158]
0x18005cab3  lea     rcx, [rbp+90h+var_C0]
0x18005cab7  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18005cabc  nop
0x18005cabd  add     rbx, 30h ; '0'
0x18005cac1  cmp     qword ptr [rbx+18h], 8
0x18005cac6  jb      short loc_18005CACD
0x18005cac8  mov     rcx, [rbx]
0x18005cacb  jmp     short loc_18005CAD0
0x18005cacd  mov     rcx, rbx; lpFileName
0x18005cad0  call    cs:__imp_DeleteFileW
0x18005cad6  test    eax, eax
0x18005cad8  jnz     short loc_18005CB18
0x18005cada  call    cs:__imp_GetLastError
0x18005cae0  cmp     eax, 2
0x18005cae3  jz      short loc_18005CB18
0x18005cae5  cmp     qword ptr [rbx+18h], 8
0x18005caea  jb      short loc_18005CAF1
0x18005caec  mov     rcx, [rbx]
0x18005caef  jmp     short loc_18005CAF4
0x18005caf1  mov     rcx, rbx
0x18005caf4  mov     [rsp+190h+var_168], eax
0x18005caf8  mov     [rsp+190h+var_170], rcx
0x18005cafd  lea     r9, aCannotDeleteTe; "Cannot delete temp copy '%s', error %ld"
0x18005cb04  mov     edx, 3Ch ; '<'; unsigned int
0x18005cb09  mov     r8d, 120h; unsigned int
0x18005cb0f  lea     rcx, [rbp+90h+var_C0]; this
0x18005cb13  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18005cb18  cmp     qword ptr [rbx+18h], 8
0x18005cb1d  jb      short loc_18005CB24
0x18005cb1f  mov     rcx, [rbx]
0x18005cb22  jmp     short loc_18005CB27
0x18005cb24  mov     rcx, rbx
0x18005cb27  mov     qword ptr [rbx+10h], 0
0x18005cb2f  xor     eax, eax
0x18005cb31  mov     [rcx], ax
0x18005cb34  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18005cb3b  mov     [rbp+90h+var_C0], rax
0x18005cb3f  lea     rcx, [rbp+90h+var_C0]; this
0x18005cb43  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18005cb48  mov     rcx, [rbp+90h+var_10]
0x18005cb4f  xor     rcx, rsp; StackCookie
0x18005cb52  call    __security_check_cookie
0x18005cb57  mov     rbx, [rsp+190h+arg_8]
0x18005cb5f  add     rsp, 190h
0x18005cb66  pop     rbp
0x18005cb67  retn
```
