# SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)

- ea: `0x180014414`
- end: `0x1800145a7`
- name: `?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ`
- size: `403`
- prototype: `void(const struct _EVENT_DESCRIPTOR *, struct SplLogType *, ...)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180002c20`

## callees

- `0x180003c4c`
- `0x180005680`
- `0x18000601c`
- `0x180014414`
- `0x1800145b0`
- `0x180014824`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180014563`
- `ntdll!EtwEventWrite` at `0x180014563`
- `ntdll!EtwEventEnabled` at `0x18001446c`
- `ntdll!EtwEventEnabled` at `0x18001446c`

## string_xrefs

- `0x180014572`: `Event: %u, EventWrite: %d`

## pseudocode

```c
void SplLogEvent2(const struct _EVENT_DESCRIPTOR *a1, struct SplLogType *a2, ...)
{
  unsigned int Id; // ebx
  unsigned int v4; // r14d
  va_list v5; // r15
  int v6; // r9d
  SplLogType *v7; // r13
  void *v8; // rax
  __int64 v9; // r10
  int v10; // r9d
  unsigned int v11; // eax
  __int64 v12; // [rsp+28h] [rbp-E0h]
  void *Value; // [rsp+38h] [rbp-D0h] BYREF
  _DWORD v14[58]; // [rsp+40h] [rbp-C8h]
  _QWORD v15[28]; // [rsp+44h] [rbp-C4h]
  SplLogType *v16; // [rsp+180h] [rbp+78h]
  va_list va; // [rsp+188h] [rbp+80h] BYREF

  va_start(va, a2);
  if ( a1 )
  {
    v16 = a2;
    if ( g_bTracingEnabled )
    {
      Id = a1->Id;
      if ( (unsigned __int8)EtwEventEnabled(g_splRegistrationHandle, a1) )
      {
        memset_0(&Value, 0, 0xF0u);
        PerfLibTelemetry::WriteDbgTraceInfo("SplLogEvent2", L"Event: %u, to be written...", Id);
        if ( v16 )
        {
          v4 = 1;
          v12 = 0;
          SplLogType::TraceValue(v16, Id, 1u);
          Value = SplLogType::GetValue(v16);
          va_copy(v5, va);
          v14[0] = v6;
          LODWORD(v15[0]) = 0;
          do
          {
            v5 += 8;
            v7 = (SplLogType *)*((_QWORD *)v5 - 1);
            if ( !v7 )
              break;
            SplLogType::TraceValue(*((SplLogType **)v5 - 1), Id, v4 + 1);
            v8 = SplLogType::GetValue(v7);
            *(_QWORD *)&v14[2 * v9 - 2] = v8;
            ++v4;
            v14[2 * v9] = v10;
            LODWORD(v15[v9]) = 0;
          }
          while ( v4 < 0xF );
        }
        else
        {
          v4 = 0;
        }
        v11 = EtwEventWrite(g_splRegistrationHandle, a1, v4, (unsigned __int64)&Value & -(__int64)(v4 != 0), v12);
        PerfLibTelemetry::WriteDbgTraceInfo("SplLogEvent2", L"Event: %u, EventWrite: %d", Id, v11);
      }
    }
  }
}

```

## disassembly

```asm
0x180014414  test    rcx, rcx
0x180014417  jz      locret_1800145A5
0x18001441d  mov     rax, rsp
0x180014420  mov     [rax+10h], rdx
0x180014424  mov     [rax+18h], r8
0x180014428  mov     [rax+20h], r9
0x18001442c  push    rbp
0x18001442d  push    rbx
0x18001442e  push    rsi
0x18001442f  push    rdi
0x180014430  push    r13
0x180014432  push    r14
0x180014434  push    r15
0x180014436  lea     rbp, [rax-68h]
0x18001443a  sub     rsp, 130h
0x180014441  mov     rax, cs:__security_cookie
0x180014448  xor     rax, rsp
0x18001444b  mov     [rbp+60h+var_40], rax
0x18001444f  cmp     cs:?g_bTracingEnabled@@3HA, 0; int g_bTracingEnabled
0x180014456  mov     rsi, rcx
0x180014459  jz      loc_180014588
0x18001445f  movzx   ebx, word ptr [rcx]
0x180014462  mov     rdx, rcx
0x180014465  mov     rcx, cs:?g_splRegistrationHandle@@3_KA; unsigned __int64 g_splRegistrationHandle
0x18001446c  call    cs:__imp_EtwEventEnabled
0x180014473  nop     dword ptr [rax+rax+00h]
0x180014478  test    al, al
0x18001447a  jz      loc_180014588
0x180014480  xor     edx, edx; Val
0x180014482  lea     rcx, [rsp+160h+var_130]; void *
0x180014487  mov     r8d, 0F0h; Size
0x18001448d  mov     edi, ebx
0x18001448f  call    memset_0
0x180014494  mov     r8d, ebx
0x180014497  lea     rdx, aEventUToBeWrit; "Event: %u, to be written..."
0x18001449e  lea     rcx, aSpllogevent2; "SplLogEvent2"
0x1800144a5  call    ?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ; PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800144aa  mov     rcx, [rbp+60h+arg_8]; this
0x1800144ae  test    rcx, rcx
0x1800144b1  jz      loc_180014543
0x1800144b7  mov     r14d, 1
0x1800144bd  mov     qword ptr [rsp+20h], 0
0x1800144c6  mov     r8d, r14d; unsigned int
0x1800144c9  mov     edx, ebx; unsigned int
0x1800144cb  call    ?TraceValue@SplLogType@@QEAAXII@Z; SplLogType::TraceValue(uint,uint)
0x1800144d0  mov     rcx, [rbp+60h+arg_8]; this
0x1800144d4  mov     r9d, [rcx+8]
0x1800144d8  call    ?GetValue@SplLogType@@QEAAPEAXXZ; SplLogType::GetValue(void)
0x1800144dd  mov     qword ptr [rsp+160h+var_130], rax
0x1800144e2  lea     r15, [rbp+60h+arg_10]
0x1800144e9  mov     [rsp+160h+var_128], r9d
0x1800144ee  mov     [rsp+160h+var_128+4], 0
0x1800144f6  lea     r15, [r15+8]
0x1800144fa  mov     r13, [r15-8]
0x1800144fe  test    r13, r13
0x180014501  jz      short loc_180014546
0x180014503  lea     ebx, [r14+1]
0x180014507  mov     edx, edi; unsigned int
0x180014509  mov     r8d, ebx; unsigned int
0x18001450c  mov     rcx, r13; this
0x18001450f  call    ?TraceValue@SplLogType@@QEAAXII@Z; SplLogType::TraceValue(uint,uint)
0x180014514  mov     r9d, [r13+8]
0x180014518  mov     rcx, r13; this
0x18001451b  mov     r10d, r14d
0x18001451e  add     r10, r10
0x180014521  call    ?GetValue@SplLogType@@QEAAPEAXXZ; SplLogType::GetValue(void)
0x180014526  mov     qword ptr [rsp+r10*8+160h+var_130], rax
0x18001452b  mov     r14d, ebx
0x18001452e  mov     [rsp+r10*8+160h+var_128], r9d
0x180014533  mov     [rsp+r10*8+160h+var_128+4], 0
0x18001453c  cmp     ebx, 0Fh
0x18001453f  jb      short loc_1800144F6
0x180014541  jmp     short loc_180014546
0x180014543  xor     r14d, r14d
0x180014546  mov     rcx, cs:?g_splRegistrationHandle@@3_KA; unsigned __int64 g_splRegistrationHandle
0x18001454d  mov     eax, r14d
0x180014550  neg     eax
0x180014552  mov     r8d, r14d
0x180014555  lea     rax, [rsp+160h+var_130]
0x18001455a  mov     rdx, rsi
0x18001455d  sbb     r9, r9
0x180014560  and     r9, rax
0x180014563  call    cs:__imp_EtwEventWrite
0x18001456a  nop     dword ptr [rax+rax+00h]
0x18001456f  mov     r8d, edi
0x180014572  lea     rdx, aEventUEventwri; "Event: %u, EventWrite: %d"
0x180014579  mov     r9d, eax
0x18001457c  lea     rcx, aSpllogevent2; "SplLogEvent2"
0x180014583  call    ?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ; PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180014588  mov     rcx, [rbp+60h+var_40]
0x18001458c  xor     rcx, rsp; StackCookie
0x18001458f  call    __security_check_cookie
0x180014594  add     rsp, 130h
0x18001459b  pop     r15
0x18001459d  pop     r14
0x18001459f  pop     r13
0x1800145a1  pop     rdi
0x1800145a2  pop     rsi
0x1800145a3  pop     rbx
0x1800145a4  pop     rbp
0x1800145a5  retn
```
