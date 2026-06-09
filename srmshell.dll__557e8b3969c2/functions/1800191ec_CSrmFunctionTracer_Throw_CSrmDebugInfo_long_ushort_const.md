# CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)

- ea: `0x1800191ec`
- end: `0x1800193e3`
- name: `?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ`
- size: `503`
- prototype: `void __noreturn(CSrmFunctionTracerBase *, const struct CSrmDebugInfo *, int, wchar_t *, ...)`
- caller_count: `8`
- callee_count: `16`
- tags: ``

## callers

- `0x180005e50`
- `0x180016f34`
- `0x1800180a0`
- `0x180018724`
- `0x1800188cc`
- `0x1800198e0`
- `0x180019c74`
- `0x18001a9f8`

## callees

- `0x180001e44`
- `0x180004850`
- `0x1800051b8`
- `0x1800054c0`
- `0x180016170`
- `0x18001639c`
- `0x180016670`
- `0x18001714c`
- `0x180017158`
- `0x180017a24`
- `0x180017e14`
- `0x180017e28`
- `0x180017e80`
- `0x180018ea8`
- `0x1800191ec`
- `0x18001957c`

## pseudocode

```c
void __noreturn CSrmFunctionTracer::Throw(
        CSrmFunctionTracerBase *a1,
        const struct CSrmDebugInfo *a2,
        int a3,
        wchar_t *a4,
        ...)
{
  unsigned __int16 *Buffer; // r14
  CSrmOutputBuffer *v8; // rcx
  int BufferSize; // eax
  va_list Args; // r8
  unsigned __int16 *v11; // rcx
  CSrmDebugInfo *v12; // rax
  CSrmDebugInfo *v13; // rax
  CSrmDebugInfo *v14; // rax
  unsigned int v15; // [rsp+20h] [rbp-99h]
  LPVOID pExceptionObject; // [rsp+40h] [rbp-79h] BYREF
  unsigned __int16 *v17; // [rsp+48h] [rbp-71h] BYREF
  _BYTE v18[8]; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int64 v19; // [rsp+58h] [rbp-61h] BYREF
  _BYTE v20[176]; // [rsp+60h] [rbp-59h] BYREF

  if ( (unsigned int)CSrmFunctionTracerBase::IsTracingEnabled(a1) && a4 )
  {
    CSrmOutputBuffer::CSrmOutputBuffer((CSrmOutputBuffer *)v18);
    if ( CSrmOutputBuffer::IsBufferValid((CSrmOutputBuffer *)v18) )
    {
      v19 = 0;
      v17 = 0;
      Buffer = CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)v18);
      BufferSize = CSrmOutputBuffer::GetBufferSize(v8);
      StringCchVPrintfExW(Buffer, BufferSize, &v17, &v19, v15, a4, Args);
      if ( v19 == 1 )
      {
        v11 = v17;
        if ( (__int64)(((char *)v17 - (char *)Buffer) & 0xFFFFFFFFFFFFFFFEuLL) > 6 )
        {
          *((_DWORD *)v17 - 1) = 3014702;
          *(v11 - 3) = 46;
        }
      }
      CSrmDebugInfo::InterpretSeverityLevel(a2, 80);
      v17 = (unsigned __int16 *)v20;
      v12 = CSrmDebugInfo::CSrmDebugInfo((CSrmDebugInfo *)v20, a2);
      CSrmFunctionTracerBase::TraceInternal(a1, v12, L"THROW");
      CSrmAutoPWSZ::CSrmAutoPWSZ((CSrmAutoPWSZ *)&pExceptionObject);
      CSrmFunctionTracerBase::GetStackTrace(a1, (struct CSrmAutoPWSZ *)&pExceptionObject);
      CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)&pExceptionObject);
      CSrmDebugInfo::InterpretSeverityLevel(a2, 80);
      v19 = (unsigned __int64)v20;
      v13 = CSrmDebugInfo::CSrmDebugInfo((CSrmDebugInfo *)v20, a2);
      CSrmFunctionTracerBase::TraceInternal(a1, v13, L"Stack Trace");
      CSrmAutoPWSZ::~CSrmAutoPWSZ(&pExceptionObject);
    }
    CSrmAutoPWSZ::CSrmAutoPWSZ((CSrmAutoPWSZ *)&pExceptionObject);
    CSrmFunctionTracerBase::GetCurrentContexts(a1, &pExceptionObject);
    CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)&pExceptionObject);
    CSrmDebugInfo::InterpretSeverityLevel(a2, 200);
    v17 = (unsigned __int16 *)v20;
    v14 = CSrmDebugInfo::CSrmDebugInfo((CSrmDebugInfo *)v20, a2);
    CSrmFunctionTracerBase::TraceInternal(a1, v14, L"THROW");
    CSrmAutoPWSZ::~CSrmAutoPWSZ(&pExceptionObject);
    CSrmOutputBuffer::~CSrmOutputBuffer((CSrmOutputBuffer *)v18);
  }
  *((_DWORD *)a1 + 2) = a3;
  LODWORD(pExceptionObject) = a3;
  throw (long *)&pExceptionObject;
}

```

## disassembly

```asm
0x1800191ec  mov     [rsp-8+arg_18], r9
0x1800191f1  mov     [rsp-8+arg_8], rdx
0x1800191f6  push    rbp
0x1800191f7  push    rbx
0x1800191f8  push    rsi
0x1800191f9  push    rdi
0x1800191fa  push    r14
0x1800191fc  lea     rbp, [rsp-37h]
0x180019201  sub     rsp, 0F0h
0x180019208  mov     esi, r8d
0x18001920b  mov     rdi, rdx
0x18001920e  mov     rbx, rcx
0x180019211  call    ?IsTracingEnabled@CSrmFunctionTracerBase@@QEAAHXZ; CSrmFunctionTracerBase::IsTracingEnabled(void)
0x180019216  xor     r14d, r14d
0x180019219  test    eax, eax
0x18001921b  jz      loc_1800193CC
0x180019221  cmp     [rbp+57h+arg_18], r14
0x180019225  jz      loc_1800193CC
0x18001922b  lea     rcx, [rbp+57h+var_C0]; this
0x18001922f  call    ??0CSrmOutputBuffer@@QEAA@XZ; CSrmOutputBuffer::CSrmOutputBuffer(void)
0x180019234  nop
0x180019235  lea     rcx, [rbp+57h+var_C0]; this
0x180019239  call    ?IsBufferValid@CSrmOutputBuffer@@QEAA_NXZ; CSrmOutputBuffer::IsBufferValid(void)
0x18001923e  test    al, al
0x180019240  jz      loc_18001935A
0x180019246  mov     [rbp+57h+var_C8], r14
0x18001924a  lea     r8, [rbp+57h+arg_20]
0x180019251  mov     [rbp+57h+var_B8], r14
0x180019255  mov     [rbp+57h+var_C8], r14
0x180019259  lea     rcx, [rbp+57h+var_C0]; this
0x18001925d  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x180019262  mov     r14, rax
0x180019265  call    ?GetBufferSize@CSrmOutputBuffer@@QEAAHXZ; CSrmOutputBuffer::GetBufferSize(void)
0x18001926a  movsxd  rdx, eax; unsigned __int64
0x18001926d  mov     [rsp+110h+Args], r8; Args
0x180019272  mov     rcx, [rbp+57h+arg_18]
0x180019276  mov     [rsp+110h+Format], rcx; Format
0x18001927b  lea     r9, [rbp+57h+var_B8]; unsigned __int64 *
0x18001927f  lea     r8, [rbp+57h+var_C8]; unsigned __int16 **
0x180019283  mov     rcx, r14; unsigned __int16 *
0x180019286  call    ?StringCchVPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGPEAD@Z; StringCchVPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,char *)
0x18001928b  cmp     [rbp+57h+var_B8], 1
0x180019290  jnz     short loc_1800192B6
0x180019292  mov     rcx, [rbp+57h+var_C8]
0x180019296  mov     rax, rcx
0x180019299  sub     rax, r14
0x18001929c  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800192a0  cmp     rax, 6
0x1800192a4  jle     short loc_1800192B6
0x1800192a6  mov     eax, 2Eh ; '.'
0x1800192ab  mov     dword ptr [rcx-4], 2E002Eh
0x1800192b2  mov     [rcx-6], ax
0x1800192b6  mov     edx, 50h ; 'P'
0x1800192bb  mov     rcx, rdi
0x1800192be  call    ?InterpretSeverityLevel@CSrmDebugInfo@@QEAAKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::InterpretSeverityLevel(_SRMDBG_SEV_ENUM)
0x1800192c3  mov     r9d, eax
0x1800192c6  lea     rax, [rbp+57h+var_B0]
0x1800192ca  mov     [rbp+57h+var_C8], rax
0x1800192ce  mov     rdx, rdi; struct CSrmDebugInfo *
0x1800192d1  lea     rcx, [rbp+57h+var_B0]; this
0x1800192d5  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x1800192da  nop
0x1800192db  mov     [rsp+110h+var_F0], r14
0x1800192e0  lea     r8, aThrow; "THROW"
0x1800192e7  mov     rdx, rax
0x1800192ea  mov     rcx, rbx
0x1800192ed  call    ?TraceInternal@CSrmFunctionTracerBase@@QEAAXUCSrmDebugInfo@@PEBGK1@Z; CSrmFunctionTracerBase::TraceInternal(CSrmDebugInfo,ushort const *,ulong,ushort const *)
0x1800192f2  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800192f6  call    ??0CSrmAutoPWSZ@@QEAA@XZ; CSrmAutoPWSZ::CSrmAutoPWSZ(void)
0x1800192fb  nop
0x1800192fc  lea     rdx, [rbp+57h+pExceptionObject]; struct CSrmAutoPWSZ *
0x180019300  mov     rcx, rbx; this
0x180019303  call    ?GetStackTrace@CSrmFunctionTracerBase@@QEAAXAEAVCSrmAutoPWSZ@@@Z; CSrmFunctionTracerBase::GetStackTrace(CSrmAutoPWSZ &)
0x180019308  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18001930c  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x180019311  mov     r10, rax
0x180019314  mov     edx, 50h ; 'P'
0x180019319  mov     rcx, rdi
0x18001931c  call    ?InterpretSeverityLevel@CSrmDebugInfo@@QEAAKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::InterpretSeverityLevel(_SRMDBG_SEV_ENUM)
0x180019321  mov     r9d, eax
0x180019324  lea     rax, [rbp+57h+var_B0]
0x180019328  mov     [rbp+57h+var_B8], rax
0x18001932c  mov     rdx, rdi; struct CSrmDebugInfo *
0x18001932f  lea     rcx, [rbp+57h+var_B0]; this
0x180019333  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x180019338  nop
0x180019339  mov     [rsp+110h+var_F0], r10
0x18001933e  lea     r8, aStackTrace; "Stack Trace"
0x180019345  mov     rdx, rax
0x180019348  mov     rcx, rbx
0x18001934b  call    ?TraceInternal@CSrmFunctionTracerBase@@QEAAXUCSrmDebugInfo@@PEBGK1@Z; CSrmFunctionTracerBase::TraceInternal(CSrmDebugInfo,ushort const *,ulong,ushort const *)
0x180019350  nop
0x180019351  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180019355  call    ??1CSrmAutoPWSZ@@QEAA@XZ; CSrmAutoPWSZ::~CSrmAutoPWSZ(void)
0x18001935a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18001935e  call    ??0CSrmAutoPWSZ@@QEAA@XZ; CSrmAutoPWSZ::CSrmAutoPWSZ(void)
0x180019363  nop
0x180019364  lea     rdx, [rbp+57h+pExceptionObject]; struct CSrmAutoPWSZ *
0x180019368  mov     rcx, rbx; this
0x18001936b  call    ?GetCurrentContexts@CSrmFunctionTracerBase@@QEAAXAEAVCSrmAutoPWSZ@@@Z; CSrmFunctionTracerBase::GetCurrentContexts(CSrmAutoPWSZ &)
0x180019370  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180019374  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x180019379  mov     r10, rax
0x18001937c  mov     edx, 0C8h
0x180019381  mov     rcx, rdi
0x180019384  call    ?InterpretSeverityLevel@CSrmDebugInfo@@QEAAKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::InterpretSeverityLevel(_SRMDBG_SEV_ENUM)
0x180019389  mov     r9d, eax
0x18001938c  lea     rax, [rbp+57h+var_B0]
0x180019390  mov     [rbp+57h+var_C8], rax
0x180019394  mov     rdx, rdi; struct CSrmDebugInfo *
0x180019397  lea     rcx, [rbp+57h+var_B0]; this
0x18001939b  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x1800193a0  nop
0x1800193a1  mov     [rsp+110h+var_F0], r10
0x1800193a6  lea     r8, aThrow; "THROW"
0x1800193ad  mov     rdx, rax
0x1800193b0  mov     rcx, rbx
0x1800193b3  call    ?TraceInternal@CSrmFunctionTracerBase@@QEAAXUCSrmDebugInfo@@PEBGK1@Z; CSrmFunctionTracerBase::TraceInternal(CSrmDebugInfo,ushort const *,ulong,ushort const *)
0x1800193b8  nop
0x1800193b9  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800193bd  call    ??1CSrmAutoPWSZ@@QEAA@XZ; CSrmAutoPWSZ::~CSrmAutoPWSZ(void)
0x1800193c2  nop
0x1800193c3  lea     rcx, [rbp+57h+var_C0]; this
0x1800193c7  call    ??1CSrmOutputBuffer@@QEAA@XZ; CSrmOutputBuffer::~CSrmOutputBuffer(void)
0x1800193cc  mov     [rbx+8], esi
0x1800193cf  mov     dword ptr [rbp+57h+pExceptionObject], esi
0x1800193d2  lea     rdx, _TI1J; pThrowInfo
0x1800193d9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800193dd  call    _CxxThrowException_0
```
