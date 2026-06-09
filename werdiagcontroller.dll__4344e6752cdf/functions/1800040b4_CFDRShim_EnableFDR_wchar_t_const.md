# CFDRShim::EnableFDR(wchar_t const *)

- ea: `0x1800040b4`
- end: `0x18000437b`
- name: `?EnableFDR@CFDRShim@@AEAAJPEB_W@Z`
- size: `711`
- prototype: `__int64 __fastcall(CFDRShim *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180005488`

## callees

- `0x180001cc6`
- `0x180001ce0`
- `0x180001d10`
- `0x1800040b4`
- `0x180004384`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x1800040ea`
- `ntdll!DbgPrintEx` at `0x1800042ab`
- `ntdll!DbgPrintEx` at `0x1800042f3`
- `ntdll!DbgPrintEx` at `0x18000433c`
- `ntdll!DbgPrintEx` at `0x180004362`
- `ntdll!DbgPrintEx` at `0x1800040ea`
- `ntdll!DbgPrintEx` at `0x1800042ab`
- `ntdll!DbgPrintEx` at `0x1800042f3`
- `ntdll!DbgPrintEx` at `0x18000433c`
- `ntdll!DbgPrintEx` at `0x180004362`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180004290`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180004290`
- `api-ms-win-eventing-legacy-l1-1-0!EnableTrace` at `0x1800042d6`
- `api-ms-win-eventing-legacy-l1-1-0!EnableTrace` at `0x1800042d6`

## string_xrefs

- `0x1800040de`: `WERDIAG: Invalid arguments: Log path cannot be null\n`
- `0x18000432e`: `WERDIAG: Failed copying string buffer. HRESULT: %08X\n`

## pseudocode

```c
__int64 __fastcall CFDRShim::EnableFDR(CFDRShim *this, const wchar_t *a2)
{
  ULONG64 *v2; // r12
  const wchar_t *v3; // r14
  const wchar_t *v6; // rax
  __int64 v7; // rdx
  unsigned int v8; // ebx
  __int64 v9; // r15
  __int64 v10; // rdx
  const WCHAR *v11; // rax
  __int64 v12; // rbp
  struct _EVENT_TRACE_PROPERTIES *v13; // rax
  struct _EVENT_TRACE_PROPERTIES *v14; // rsi
  ULONG v15; // ecx
  unsigned __int64 v16; // rdx
  _WORD *v17; // r8
  __int64 v18; // rax
  _WORD *v19; // rcx
  ULONG started; // eax
  ULONG v21; // eax
  signed int v22; // edi
  ULONG v23; // [rsp+80h] [rbp+8h]

  v2 = (ULONG64 *)((char *)this + 288);
  *((_QWORD *)this + 36) = 0;
  v3 = a2;
  if ( !a2 )
  {
    DbgPrintEx(0x96u, 0, "WERDIAG: Invalid arguments: Log path cannot be null\n");
    return 2147942487LL;
  }
  v6 = a2;
  v7 = 0x7FFFFFFF;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v7;
  }
  while ( v7 );
  v8 = v7 == 0 ? 0x80070057 : 0;
  v9 = (0x7FFFFFFF - v7) & -(__int64)(v7 != 0);
  if ( v7 )
  {
    v10 = 0x7FFFFFFF;
    v11 = L"FDR Tracing Session";
    do
    {
      if ( !*v11 )
        break;
      ++v11;
      --v10;
    }
    while ( v10 );
    v8 = v10 == 0 ? 0x80070057 : 0;
    v12 = (0x7FFFFFFF - v10) & -(__int64)(v10 != 0);
    if ( v10 )
    {
      v23 = 2 * (v9 + v12) + 124;
      v13 = (struct _EVENT_TRACE_PROPERTIES *)operator new(v23, (const struct std::nothrow_t *)&std::nothrow);
      v14 = v13;
      if ( !v13 )
      {
        DbgPrintEx(0x96u, 0, "WERDIAG: Unable to allocate %d bytes for properties structure.\n", v23);
        return v8;
      }
      memset_0(v13, 0, sizeof(struct _EVENT_TRACE_PROPERTIES));
      v15 = 2 * v12 + 122;
      v14->Wnode.BufferSize = v23;
      v16 = v9 + 1;
      v14->Wnode.Flags = 0x20000;
      v14->Wnode.ClientContext = 1;
      v17 = (_WORD *)((char *)v14 + v15);
      v14->Wnode.Guid = ControlGuid;
      v14->LogFileMode = 16910338;
      v14->LoggerNameOffset = 120;
      v14->LogFileNameOffset = v15;
      v14->MaximumFileSize = *((_DWORD *)this + 1);
      v14->BufferSize = 1;
      v14->FlushTimer = 0;
      if ( v9 == -1 )
      {
        v8 = -2147024809;
      }
      else if ( v16 <= 0x7FFFFFFF )
      {
        v18 = 2147483646;
        do
        {
          if ( !v18 )
            break;
          if ( !*v3 )
            break;
          *v17++ = *v3++;
          --v18;
          --v16;
        }
        while ( v16 );
        v19 = v17 - 1;
        v8 = v16 == 0 ? 0x8007007A : 0;
        if ( v16 )
          v19 = v17;
        *v19 = 0;
        if ( v16 )
        {
          started = StartTraceW(v2, L"FDR Tracing Session", v14);
          if ( started )
          {
            DbgPrintEx(0x96u, 0, "WERDIAG: StartTrace failed for the internal provider. Win32 error: %08X\n", started);
            v8 = -2147467259;
          }
          else
          {
            v21 = EnableTrace(1u, 1u, 4u, &ControlGuid, *v2);
            v22 = v21;
            if ( v21 )
            {
              DbgPrintEx(0x96u, 0, "WERDIAG: Failed enabling internal trace provider. Win32 error: %08X\n", v21);
              if ( v22 > 0 )
                v22 = (unsigned __int16)v22 | 0x80070000;
              if ( v22 >= 0 )
                v22 = -2147467259;
              v8 = v22;
            }
            else
            {
              CFDRShim::EnableLogProviders(this);
              v8 = 0;
            }
          }
          goto LABEL_35;
        }
      }
      else
      {
        v8 = -2147024809;
        *v17 = 0;
      }
      DbgPrintEx(0x96u, 0, "WERDIAG: Failed copying string buffer. HRESULT: %08X\n", v8);
LABEL_35:
      operator delete(v14);
      return v8;
    }
  }
  DbgPrintEx(0x96u, 0, "WERDIAG: Failed determining string length. HRESULT: %08X\n", v8);
  return v8;
}

```

## disassembly

```asm
0x1800040b4  push    rbx
0x1800040b6  push    rbp
0x1800040b7  push    rsi
0x1800040b8  push    rdi
0x1800040b9  push    r12
0x1800040bb  push    r13
0x1800040bd  push    r14
0x1800040bf  push    r15
0x1800040c1  sub     rsp, 38h
0x1800040c5  xor     r8d, r8d
0x1800040c8  lea     r12, [rcx+120h]
0x1800040cf  mov     [r12], r8
0x1800040d3  mov     r14, rdx
0x1800040d6  mov     r13, rcx
0x1800040d9  test    rdx, rdx
0x1800040dc  jnz     short loc_1800040FA
0x1800040de  lea     r8, aWerdiagInvalid; "WERDIAG: Invalid arguments: Log path ca"...
0x1800040e5  mov     ecx, 96h; ComponentId
0x1800040ea  call    cs:__imp_DbgPrintEx
0x1800040f0  mov     eax, 80070057h
0x1800040f5  jmp     loc_18000436A
0x1800040fa  mov     r9d, 7FFFFFFFh
0x180004100  mov     rax, r14
0x180004103  mov     edx, r9d
0x180004106  cmp     [rax], r8w
0x18000410a  jz      short loc_180004116
0x18000410c  add     rax, 2
0x180004110  sub     rdx, 1
0x180004114  jnz     short loc_180004106
0x180004116  mov     rax, rdx
0x180004119  mov     edi, 80070057h
0x18000411e  neg     rax
0x180004121  mov     rcx, r9
0x180004124  mov     rax, rdx
0x180004127  sbb     ebx, ebx
0x180004129  sub     rcx, rdx
0x18000412c  not     ebx
0x18000412e  and     ebx, edi
0x180004130  neg     rax
0x180004133  sbb     r15, r15
0x180004136  and     r15, rcx
0x180004139  test    rdx, rdx
0x18000413c  jnz     short loc_18000414D
0x18000413e  mov     r9d, ebx
0x180004141  lea     r8, aWerdiagFailedD_2; "WERDIAG: Failed determining string leng"...
0x180004148  jmp     loc_18000435B
0x18000414d  mov     rdx, r9
0x180004150  lea     rax, InstanceName; "FDR Tracing Session"
0x180004157  cmp     [rax], r8w
0x18000415b  jz      short loc_180004167
0x18000415d  add     rax, 2
0x180004161  sub     rdx, 1
0x180004165  jnz     short loc_180004157
0x180004167  mov     rax, rdx
0x18000416a  mov     rcx, r9
0x18000416d  neg     rax
0x180004170  mov     rax, rdx
0x180004173  sbb     ebx, ebx
0x180004175  sub     rcx, rdx
0x180004178  not     ebx
0x18000417a  and     ebx, edi
0x18000417c  neg     rax
0x18000417f  sbb     rbp, rbp
0x180004182  and     rbp, rcx
0x180004185  test    rdx, rdx
0x180004188  jz      short loc_18000413E
0x18000418a  lea     eax, [r15+rbp]
0x18000418e  lea     eax, ds:7Ch[rax*2]
0x180004195  mov     ecx, eax; unsigned __int64
0x180004197  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000419e  mov     [rsp+78h+arg_0], eax
0x1800041a5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800041aa  mov     rsi, rax
0x1800041ad  test    rax, rax
0x1800041b0  jz      loc_18000434C
0x1800041b6  mov     ebx, 78h ; 'x'
0x1800041bb  xor     edx, edx; Val
0x1800041bd  mov     r8d, ebx; Size
0x1800041c0  mov     rcx, rax; void *
0x1800041c3  call    memset_0
0x1800041c8  mov     r9d, [rsp+78h+arg_0]
0x1800041d0  lea     ecx, ds:7Ah[rbp*2]
0x1800041d7  mov     [rsi], r9d
0x1800041da  lea     rdx, [r15+1]
0x1800041de  mov     dword ptr [rsi+2Ch], 20000h
0x1800041e5  xor     ebp, ebp
0x1800041e7  mov     dword ptr [rsi+28h], 1
0x1800041ee  movups  xmm0, xmmword ptr cs:ControlGuid.Data1
0x1800041f5  mov     r8d, ecx
0x1800041f8  add     r8, rsi
0x1800041fb  movdqu  xmmword ptr [rsi+18h], xmm0
0x180004200  mov     dword ptr [rsi+40h], 1020802h
0x180004207  mov     [rsi+74h], ebx
0x18000420a  mov     [rsi+70h], ecx
0x18000420d  mov     eax, [r13+4]
0x180004211  mov     [rsi+3Ch], eax
0x180004214  mov     dword ptr [rsi+30h], 1
0x18000421b  mov     [rsi+44h], ebp
0x18000421e  test    rdx, rdx
0x180004221  jz      loc_180004320
0x180004227  cmp     rdx, 7FFFFFFFh
0x18000422e  jbe     short loc_180004237
0x180004230  mov     ebx, edi
0x180004232  jmp     loc_180004327
0x180004237  mov     eax, 7FFFFFFEh
0x18000423c  test    rax, rax
0x18000423f  jz      short loc_18000425F
0x180004241  movzx   ecx, word ptr [r14]
0x180004245  test    cx, cx
0x180004248  jz      short loc_18000425F
0x18000424a  mov     [r8], cx
0x18000424e  add     r14, 2
0x180004252  add     r8, 2
0x180004256  dec     rax
0x180004259  sub     rdx, 1
0x18000425d  jnz     short loc_18000423C
0x18000425f  mov     rax, rdx
0x180004262  lea     rcx, [r8-2]
0x180004266  neg     rax
0x180004269  sbb     ebx, ebx
0x18000426b  not     ebx
0x18000426d  and     ebx, 8007007Ah
0x180004273  test    rdx, rdx
0x180004276  cmovnz  rcx, r8
0x18000427a  mov     [rcx], bp
0x18000427d  jz      loc_18000432B
0x180004283  mov     r8, rsi; Properties
0x180004286  lea     rdx, InstanceName; "FDR Tracing Session"
0x18000428d  mov     rcx, r12; TraceHandle
0x180004290  call    cs:__imp_StartTraceW
0x180004296  test    eax, eax
0x180004298  jz      short loc_1800042BB
0x18000429a  mov     r9d, eax
0x18000429d  lea     r8, aWerdiagStarttr; "WERDIAG: StartTrace failed for the inte"...
0x1800042a4  xor     edx, edx; Level
0x1800042a6  mov     ecx, 96h; ComponentId
0x1800042ab  call    cs:__imp_DbgPrintEx
0x1800042b1  mov     ebx, 80004005h
0x1800042b6  jmp     loc_180004342
0x1800042bb  mov     rax, [r12]
0x1800042bf  lea     r9, ControlGuid; ControlGuid
0x1800042c6  mov     edx, 1; EnableFlag
0x1800042cb  mov     [rsp+78h+TraceHandle], rax; TraceHandle
0x1800042d0  mov     ecx, edx; Enable
0x1800042d2  lea     r8d, [rdx+3]; EnableLevel
0x1800042d6  call    cs:__imp_EnableTrace
0x1800042dc  mov     edi, eax
0x1800042de  test    eax, eax
0x1800042e0  jz      short loc_180004314
0x1800042e2  mov     r9d, eax
0x1800042e5  lea     r8, aWerdiagFailedE; "WERDIAG: Failed enabling internal trace"...
0x1800042ec  xor     edx, edx; Level
0x1800042ee  mov     ecx, 96h; ComponentId
0x1800042f3  call    cs:__imp_DbgPrintEx
0x1800042f9  test    edi, edi
0x1800042fb  jle     short loc_180004306
0x1800042fd  movzx   edi, di
0x180004300  or      edi, 80070000h
0x180004306  mov     ebx, 80004005h
0x18000430b  test    edi, edi
0x18000430d  cmovns  edi, ebx
0x180004310  mov     ebx, edi
0x180004312  jmp     short loc_180004342
0x180004314  mov     rcx, r13; this
0x180004317  call    ?EnableLogProviders@CFDRShim@@QEAAJXZ; CFDRShim::EnableLogProviders(void)
0x18000431c  mov     ebx, ebp
0x18000431e  jmp     short loc_180004342
0x180004320  mov     ebx, edi
0x180004322  test    rdx, rdx
0x180004325  jz      short loc_18000432B
0x180004327  mov     [r8], bp
0x18000432b  mov     r9d, ebx
0x18000432e  lea     r8, aWerdiagFailedC_6; "WERDIAG: Failed copying string buffer. "...
0x180004335  xor     edx, edx; Level
0x180004337  mov     ecx, 96h; ComponentId
0x18000433c  call    cs:__imp_DbgPrintEx
0x180004342  mov     rcx, rsi; Block
0x180004345  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000434a  jmp     short loc_180004368
0x18000434c  mov     r9d, [rsp+78h+arg_0]
0x180004354  lea     r8, aWerdiagUnableT; "WERDIAG: Unable to allocate %d bytes fo"...
0x18000435b  xor     edx, edx; Level
0x18000435d  mov     ecx, 96h; ComponentId
0x180004362  call    cs:__imp_DbgPrintEx
0x180004368  mov     eax, ebx
0x18000436a  add     rsp, 38h
0x18000436e  pop     r15
0x180004370  pop     r14
0x180004372  pop     r13
0x180004374  pop     r12
0x180004376  pop     rdi
0x180004377  pop     rsi
0x180004378  pop     rbp
0x180004379  pop     rbx
0x18000437a  retn
```
