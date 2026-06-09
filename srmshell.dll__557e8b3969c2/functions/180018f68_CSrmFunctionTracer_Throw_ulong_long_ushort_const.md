# CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)

- ea: `0x180018f68`
- end: `0x1800191e4`
- name: `?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ`
- size: `636`
- prototype: `void __noreturn(CSrmFunctionTracer *this, int, int, CSrmOutputBuffer *, ...)`
- caller_count: `25`
- callee_count: `23`
- tags: ``

## callers

- `0x180002658`
- `0x180002960`
- `0x180002b10`
- `0x1800059e0`
- `0x180005ce0`
- `0x180005fa0`
- `0x1800061d0`
- `0x180006688`
- `0x180006b50`
- `0x180007d44`
- `0x180008288`
- `0x180008408`
- `0x1800096c0`
- `0x180009d18`
- `0x18000a460`
- `0x18000ace8`
- `0x18000dd70`
- `0x18000e224`
- `0x18000ecb8`
- `0x18000eeb4`
- `0x18000f4b0`
- `0x180017158`
- `0x180018af0`
- `0x18001a540`
- `0x18001ae30`

## callees

- `0x180001e44`
- `0x180004850`
- `0x1800051b8`
- `0x1800054c0`
- `0x1800083fc`
- `0x18000f424`
- `0x180016170`
- `0x1800161e8`
- `0x18001639c`
- `0x180016518`
- `0x180016670`
- `0x18001714c`
- `0x180017158`
- `0x180017a00`
- `0x180017a0c`
- `0x180017a18`
- `0x180017a24`
- `0x180017e14`
- `0x180017e28`
- `0x180017e80`
- `0x180018ea8`
- `0x180018f68`
- `0x18001957c`

## pseudocode

```c
void __noreturn CSrmFunctionTracer::Throw(CSrmFunctionTracer *this, int a2, int a3, CSrmOutputBuffer *a4, ...)
{
  CSrmFunctionTracerBase *v7; // rcx
  CSrmFunctionTracerBase *v8; // rcx
  CSrmFunctionTracerBase *v9; // rcx
  const unsigned __int16 *FileName; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // r10d
  unsigned __int16 *Buffer; // rdi
  int BufferSize; // eax
  wchar_t *Format; // rcx
  va_list Args; // r8
  unsigned __int16 *v18; // rcx
  int v19; // eax
  CSrmDebugInfo *v20; // rax
  CSrmDebugInfo *v21; // rax
  CSrmDebugInfo *v22; // rax
  unsigned int v23; // [rsp+20h] [rbp-E0h]
  LPVOID pExceptionObject; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v25; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v26; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v27[8]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v28[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v29[144]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v30[176]; // [rsp+100h] [rbp+0h] BYREF

  if ( (unsigned int)CSrmFunctionTracerBase::IsTracingEnabled(this) )
  {
    CSrmOutputBuffer::CSrmOutputBuffer((CSrmOutputBuffer *)v27);
    CSrmFunctionTracerBase::GetModuleIndex(this);
    CSrmFunctionTracerBase::GetFunctionName(v7);
    CSrmFunctionTracerBase::GetFileAlias(v8);
    FileName = CSrmFunctionTracerBase::GetFileName(v9);
    CSrmDebugInfo::CSrmDebugInfo((__int64)v29, (__int64)FileName, v11, v12, a2, v13);
    if ( CSrmOutputBuffer::IsBufferValid((CSrmOutputBuffer *)v27) )
    {
      Buffer = CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)v27);
      if ( a4 )
      {
        v28[0] = 0;
        v25 = 0;
        BufferSize = CSrmOutputBuffer::GetBufferSize(a4);
        StringCchVPrintfExW(Buffer, BufferSize, &v25, v28, v23, Format, Args);
        if ( v28[0] == 1 )
        {
          v18 = v25;
          if ( (__int64)(((char *)v25 - (char *)Buffer) & 0xFFFFFFFFFFFFFFFEuLL) > 6 )
          {
            *((_DWORD *)v25 - 1) = 3014702;
            *(v18 - 3) = 46;
          }
        }
      }
      else
      {
        v19 = CSrmOutputBuffer::GetBufferSize(0);
        StringCchPrintfW(Buffer, v19, L"Exception: %#x", *((unsigned int *)this + 2));
      }
      CSrmDebugInfo::InterpretSeverityLevel(v29, 80);
      v25 = (unsigned __int16 *)v30;
      v20 = CSrmDebugInfo::CSrmDebugInfo((CSrmDebugInfo *)v30, (const struct CSrmDebugInfo *)v29);
      CSrmFunctionTracerBase::TraceInternal(this, v20, L"THROW");
      CSrmAutoPWSZ::CSrmAutoPWSZ((CSrmAutoPWSZ *)&v26);
      CSrmFunctionTracerBase::GetStackTrace(this, (struct CSrmAutoPWSZ *)&v26);
      CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)&v26);
      CSrmDebugInfo::InterpretSeverityLevel(v29, 80);
      v28[0] = (unsigned __int64)v30;
      v21 = CSrmDebugInfo::CSrmDebugInfo((CSrmDebugInfo *)v30, (const struct CSrmDebugInfo *)v29);
      CSrmFunctionTracerBase::TraceInternal(this, v21, L"Stack Trace");
      CSrmAutoPWSZ::CSrmAutoPWSZ((CSrmAutoPWSZ *)&pExceptionObject);
      CSrmFunctionTracerBase::GetCurrentContexts(this, &pExceptionObject);
      CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)&pExceptionObject);
      CSrmDebugInfo::InterpretSeverityLevel(v29, 200);
      v28[1] = (unsigned __int64)v30;
      v22 = CSrmDebugInfo::CSrmDebugInfo((CSrmDebugInfo *)v30, (const struct CSrmDebugInfo *)v29);
      CSrmFunctionTracerBase::TraceInternal(this, v22, L"THROW");
      CSrmAutoPWSZ::~CSrmAutoPWSZ(&pExceptionObject);
      CSrmAutoPWSZ::~CSrmAutoPWSZ(&v26);
    }
    CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)v29);
    CSrmOutputBuffer::~CSrmOutputBuffer((CSrmOutputBuffer *)v27);
  }
  *((_DWORD *)this + 2) = a3;
  LODWORD(pExceptionObject) = a3;
  throw (long *)&pExceptionObject;
}

```

## disassembly

```asm
0x180018f68  mov     [rsp-8+arg_18], r9
0x180018f6d  push    rbp
0x180018f6e  push    rbx
0x180018f6f  push    rsi
0x180018f70  push    rdi
0x180018f71  lea     rbp, [rsp-98h]
0x180018f79  sub     rsp, 198h
0x180018f80  mov     esi, r8d
0x180018f83  mov     edi, edx
0x180018f85  mov     rbx, rcx
0x180018f88  call    ?IsTracingEnabled@CSrmFunctionTracerBase@@QEAAHXZ; CSrmFunctionTracerBase::IsTracingEnabled(void)
0x180018f8d  test    eax, eax
0x180018f8f  jz      loc_1800191CB
0x180018f95  lea     rcx, [rsp+1B0h+var_158]; this
0x180018f9a  call    ??0CSrmOutputBuffer@@QEAA@XZ; CSrmOutputBuffer::CSrmOutputBuffer(void)
0x180018f9f  nop
0x180018fa0  mov     rcx, rbx; this
0x180018fa3  call    ?GetModuleIndex@CSrmFunctionTracerBase@@QEAAKXZ; CSrmFunctionTracerBase::GetModuleIndex(void)
0x180018fa8  mov     r10d, eax
0x180018fab  call    ?GetFunctionName@CSrmFunctionTracerBase@@QEAAPEBGXZ; CSrmFunctionTracerBase::GetFunctionName(void)
0x180018fb0  mov     r9, rax
0x180018fb3  call    ?GetFileAlias@CSrmFunctionTracerBase@@QEAAPEBGXZ; CSrmFunctionTracerBase::GetFileAlias(void)
0x180018fb8  mov     r8, rax
0x180018fbb  call    ?GetFileName@CSrmFunctionTracerBase@@QEAAPEBGXZ; CSrmFunctionTracerBase::GetFileName(void)
0x180018fc0  mov     rdx, rax
0x180018fc3  mov     dword ptr [rsp+1B0h+Format], r10d
0x180018fc8  mov     [rsp+1B0h+var_190], edi; unsigned int
0x180018fcc  lea     rcx, [rsp+1B0h+var_140]
0x180018fd1  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180018fd6  nop
0x180018fd7  lea     rcx, [rsp+1B0h+var_158]; this
0x180018fdc  call    ?IsBufferValid@CSrmOutputBuffer@@QEAA_NXZ; CSrmOutputBuffer::IsBufferValid(void)
0x180018fe1  test    al, al
0x180018fe3  jz      loc_1800191B6
0x180018fe9  lea     rcx, [rsp+1B0h+var_158]; this
0x180018fee  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x180018ff3  mov     rdi, rax
0x180018ff6  mov     rcx, [rbp+0B0h+arg_18]; this
0x180018ffd  test    rcx, rcx
0x180019000  jz      short loc_180019077
0x180019002  mov     [rsp+1B0h+var_168], 0
0x18001900b  lea     r8, [rbp+0B0h+arg_20]
0x180019012  mov     [rsp+1B0h+var_150], 0
0x18001901b  mov     [rsp+1B0h+var_168], 0
0x180019024  call    ?GetBufferSize@CSrmOutputBuffer@@QEAAHXZ; CSrmOutputBuffer::GetBufferSize(void)
0x180019029  movsxd  rdx, eax; unsigned __int64
0x18001902c  mov     [rsp+1B0h+Args], r8; Args
0x180019031  mov     [rsp+1B0h+Format], rcx; Format
0x180019036  lea     r9, [rsp+1B0h+var_150]; unsigned __int64 *
0x18001903b  lea     r8, [rsp+1B0h+var_168]; unsigned __int16 **
0x180019040  mov     rcx, rdi; unsigned __int16 *
0x180019043  call    ?StringCchVPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGPEAD@Z; StringCchVPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,char *)
0x180019048  cmp     [rsp+1B0h+var_150], 1
0x18001904e  jnz     short loc_180019092
0x180019050  mov     rcx, [rsp+1B0h+var_168]
0x180019055  mov     rax, rcx
0x180019058  sub     rax, rdi
0x18001905b  and     rax, 0FFFFFFFFFFFFFFFEh
0x18001905f  cmp     rax, 6
0x180019063  jle     short loc_180019092
0x180019065  mov     eax, 2Eh ; '.'
0x18001906a  mov     dword ptr [rcx-4], 2E002Eh
0x180019071  mov     [rcx-6], ax
0x180019075  jmp     short loc_180019092
0x180019077  call    ?GetBufferSize@CSrmOutputBuffer@@QEAAHXZ; CSrmOutputBuffer::GetBufferSize(void)
0x18001907c  movsxd  rdx, eax; unsigned __int64
0x18001907f  mov     r9d, [rbx+8]
0x180019083  lea     r8, aExceptionX; "Exception: %#x"
0x18001908a  mov     rcx, rdi; unsigned __int16 *
0x18001908d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019092  mov     edx, 50h ; 'P'
0x180019097  lea     rcx, [rsp+1B0h+var_140]
0x18001909c  call    ?InterpretSeverityLevel@CSrmDebugInfo@@QEAAKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::InterpretSeverityLevel(_SRMDBG_SEV_ENUM)
0x1800190a1  mov     r9d, eax
0x1800190a4  lea     rax, [rbp+0B0h+var_B0]
0x1800190a8  mov     [rsp+1B0h+var_168], rax
0x1800190ad  lea     rdx, [rsp+1B0h+var_140]; struct CSrmDebugInfo *
0x1800190b2  lea     rcx, [rbp+0B0h+var_B0]; this
0x1800190b6  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x1800190bb  nop
0x1800190bc  mov     qword ptr [rsp+1B0h+var_190], rdi
0x1800190c1  lea     r8, aThrow; "THROW"
0x1800190c8  mov     rdx, rax
0x1800190cb  mov     rcx, rbx
0x1800190ce  call    ?TraceInternal@CSrmFunctionTracerBase@@QEAAXUCSrmDebugInfo@@PEBGK1@Z; CSrmFunctionTracerBase::TraceInternal(CSrmDebugInfo,ushort const *,ulong,ushort const *)
0x1800190d3  lea     rcx, [rsp+1B0h+var_160]; this
0x1800190d8  call    ??0CSrmAutoPWSZ@@QEAA@XZ; CSrmAutoPWSZ::CSrmAutoPWSZ(void)
0x1800190dd  nop
0x1800190de  lea     rdx, [rsp+1B0h+var_160]; struct CSrmAutoPWSZ *
0x1800190e3  mov     rcx, rbx; this
0x1800190e6  call    ?GetStackTrace@CSrmFunctionTracerBase@@QEAAXAEAVCSrmAutoPWSZ@@@Z; CSrmFunctionTracerBase::GetStackTrace(CSrmAutoPWSZ &)
0x1800190eb  lea     rcx, [rsp+1B0h+var_160]; this
0x1800190f0  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x1800190f5  mov     r10, rax
0x1800190f8  mov     edx, 50h ; 'P'
0x1800190fd  lea     rcx, [rsp+1B0h+var_140]
0x180019102  call    ?InterpretSeverityLevel@CSrmDebugInfo@@QEAAKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::InterpretSeverityLevel(_SRMDBG_SEV_ENUM)
0x180019107  mov     r9d, eax
0x18001910a  lea     rax, [rbp+0B0h+var_B0]
0x18001910e  mov     [rsp+1B0h+var_150], rax
0x180019113  lea     rdx, [rsp+1B0h+var_140]; struct CSrmDebugInfo *
0x180019118  lea     rcx, [rbp+0B0h+var_B0]; this
0x18001911c  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x180019121  nop
0x180019122  mov     qword ptr [rsp+1B0h+var_190], r10
0x180019127  lea     r8, aStackTrace; "Stack Trace"
0x18001912e  mov     rdx, rax
0x180019131  mov     rcx, rbx
0x180019134  call    ?TraceInternal@CSrmFunctionTracerBase@@QEAAXUCSrmDebugInfo@@PEBGK1@Z; CSrmFunctionTracerBase::TraceInternal(CSrmDebugInfo,ushort const *,ulong,ushort const *)
0x180019139  lea     rcx, [rsp+1B0h+pExceptionObject]; this
0x18001913e  call    ??0CSrmAutoPWSZ@@QEAA@XZ; CSrmAutoPWSZ::CSrmAutoPWSZ(void)
0x180019143  nop
0x180019144  lea     rdx, [rsp+1B0h+pExceptionObject]; struct CSrmAutoPWSZ *
0x180019149  mov     rcx, rbx; this
0x18001914c  call    ?GetCurrentContexts@CSrmFunctionTracerBase@@QEAAXAEAVCSrmAutoPWSZ@@@Z; CSrmFunctionTracerBase::GetCurrentContexts(CSrmAutoPWSZ &)
0x180019151  lea     rcx, [rsp+1B0h+pExceptionObject]; this
0x180019156  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x18001915b  mov     r10, rax
0x18001915e  mov     edx, 0C8h
0x180019163  lea     rcx, [rsp+1B0h+var_140]
0x180019168  call    ?InterpretSeverityLevel@CSrmDebugInfo@@QEAAKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::InterpretSeverityLevel(_SRMDBG_SEV_ENUM)
0x18001916d  mov     r9d, eax
0x180019170  lea     rax, [rbp+0B0h+var_B0]
0x180019174  mov     [rsp+1B0h+var_148], rax
0x180019179  lea     rdx, [rsp+1B0h+var_140]; struct CSrmDebugInfo *
0x18001917e  lea     rcx, [rbp+0B0h+var_B0]; this
0x180019182  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x180019187  nop
0x180019188  mov     qword ptr [rsp+1B0h+var_190], r10
0x18001918d  lea     r8, aThrow; "THROW"
0x180019194  mov     rdx, rax
0x180019197  mov     rcx, rbx
0x18001919a  call    ?TraceInternal@CSrmFunctionTracerBase@@QEAAXUCSrmDebugInfo@@PEBGK1@Z; CSrmFunctionTracerBase::TraceInternal(CSrmDebugInfo,ushort const *,ulong,ushort const *)
0x18001919f  nop
0x1800191a0  lea     rcx, [rsp+1B0h+pExceptionObject]; this
0x1800191a5  call    ??1CSrmAutoPWSZ@@QEAA@XZ; CSrmAutoPWSZ::~CSrmAutoPWSZ(void)
0x1800191aa  nop
0x1800191ab  lea     rcx, [rsp+1B0h+var_160]; this
0x1800191b0  call    ??1CSrmAutoPWSZ@@QEAA@XZ; CSrmAutoPWSZ::~CSrmAutoPWSZ(void)
0x1800191b5  nop
0x1800191b6  lea     rcx, [rsp+1B0h+var_140]; this
0x1800191bb  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x1800191c0  nop
0x1800191c1  lea     rcx, [rsp+1B0h+var_158]; this
0x1800191c6  call    ??1CSrmOutputBuffer@@QEAA@XZ; CSrmOutputBuffer::~CSrmOutputBuffer(void)
0x1800191cb  mov     [rbx+8], esi
0x1800191ce  mov     dword ptr [rsp+1B0h+pExceptionObject], esi
0x1800191d2  lea     rdx, _TI1J; pThrowInfo
0x1800191d9  lea     rcx, [rsp+1B0h+pExceptionObject]; pExceptionObject
0x1800191de  call    _CxxThrowException_0
```
