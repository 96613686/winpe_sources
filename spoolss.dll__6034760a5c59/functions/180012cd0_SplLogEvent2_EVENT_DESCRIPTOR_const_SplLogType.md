# SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)

- ea: `0x180012cd0`
- end: `0x180012e56`
- name: `?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ`
- size: `390`
- prototype: `void(const struct _EVENT_DESCRIPTOR *, struct SplLogType *, ...)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800029f0`

## callees

- `0x180003950`
- `0x180005320`
- `0x180005cac`
- `0x180012cd0`
- `0x180012e5c`
- `0x1800130c4`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180012e19`
- `ntdll!EtwEventWrite` at `0x180012e19`
- `ntdll!EtwEventEnabled` at `0x180012d28`
- `ntdll!EtwEventEnabled` at `0x180012d28`

## string_xrefs

- `0x180012e22`: `Event: %u, EventWrite: %d`

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
0x180012cd0  test    rcx, rcx
0x180012cd3  jz      locret_180012E55
0x180012cd9  mov     rax, rsp
0x180012cdc  mov     [rax+10h], rdx
0x180012ce0  mov     [rax+18h], r8
0x180012ce4  mov     [rax+20h], r9
0x180012ce8  push    rbp
0x180012ce9  push    rbx
0x180012cea  push    rsi
0x180012ceb  push    rdi
0x180012cec  push    r13
0x180012cee  push    r14
0x180012cf0  push    r15
0x180012cf2  lea     rbp, [rax-68h]
0x180012cf6  sub     rsp, 130h
0x180012cfd  mov     rax, cs:__security_cookie
0x180012d04  xor     rax, rsp
0x180012d07  mov     [rbp+60h+var_40], rax
0x180012d0b  cmp     cs:?g_bTracingEnabled@@3HA, 0; int g_bTracingEnabled
0x180012d12  mov     rsi, rcx
0x180012d15  jz      loc_180012E38
0x180012d1b  movzx   ebx, word ptr [rcx]
0x180012d1e  mov     rdx, rcx
0x180012d21  mov     rcx, cs:?g_splRegistrationHandle@@3_KA; unsigned __int64 g_splRegistrationHandle
0x180012d28  call    cs:__imp_EtwEventEnabled
0x180012d2e  test    al, al
0x180012d30  jz      loc_180012E38
0x180012d36  xor     edx, edx; Val
0x180012d38  lea     rcx, [rsp+160h+var_130]; void *
0x180012d3d  mov     r8d, 0F0h; Size
0x180012d43  mov     edi, ebx
0x180012d45  call    memset_0
0x180012d4a  mov     r8d, ebx
0x180012d4d  lea     rdx, aEventUToBeWrit; "Event: %u, to be written..."
0x180012d54  lea     rcx, aSpllogevent2; "SplLogEvent2"
0x180012d5b  call    ?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ; PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180012d60  mov     rcx, [rbp+60h+arg_8]; this
0x180012d64  test    rcx, rcx
0x180012d67  jz      loc_180012DF9
0x180012d6d  mov     r14d, 1
0x180012d73  mov     qword ptr [rsp+20h], 0
0x180012d7c  mov     r8d, r14d; unsigned int
0x180012d7f  mov     edx, ebx; unsigned int
0x180012d81  call    ?TraceValue@SplLogType@@QEAAXII@Z; SplLogType::TraceValue(uint,uint)
0x180012d86  mov     rcx, [rbp+60h+arg_8]; this
0x180012d8a  mov     r9d, [rcx+8]
0x180012d8e  call    ?GetValue@SplLogType@@QEAAPEAXXZ; SplLogType::GetValue(void)
0x180012d93  mov     qword ptr [rsp+160h+var_130], rax
0x180012d98  lea     r15, [rbp+60h+arg_10]
0x180012d9f  mov     [rsp+160h+var_128], r9d
0x180012da4  mov     [rsp+160h+var_128+4], 0
0x180012dac  lea     r15, [r15+8]
0x180012db0  mov     r13, [r15-8]
0x180012db4  test    r13, r13
0x180012db7  jz      short loc_180012DFC
0x180012db9  lea     ebx, [r14+1]
0x180012dbd  mov     edx, edi; unsigned int
0x180012dbf  mov     r8d, ebx; unsigned int
0x180012dc2  mov     rcx, r13; this
0x180012dc5  call    ?TraceValue@SplLogType@@QEAAXII@Z; SplLogType::TraceValue(uint,uint)
0x180012dca  mov     r9d, [r13+8]
0x180012dce  mov     rcx, r13; this
0x180012dd1  mov     r10d, r14d
0x180012dd4  add     r10, r10
0x180012dd7  call    ?GetValue@SplLogType@@QEAAPEAXXZ; SplLogType::GetValue(void)
0x180012ddc  mov     qword ptr [rsp+r10*8+160h+var_130], rax
0x180012de1  mov     r14d, ebx
0x180012de4  mov     [rsp+r10*8+160h+var_128], r9d
0x180012de9  mov     [rsp+r10*8+160h+var_128+4], 0
0x180012df2  cmp     ebx, 0Fh
0x180012df5  jb      short loc_180012DAC
0x180012df7  jmp     short loc_180012DFC
0x180012df9  xor     r14d, r14d
0x180012dfc  mov     rcx, cs:?g_splRegistrationHandle@@3_KA; unsigned __int64 g_splRegistrationHandle
0x180012e03  mov     eax, r14d
0x180012e06  neg     eax
0x180012e08  mov     r8d, r14d
0x180012e0b  lea     rax, [rsp+160h+var_130]
0x180012e10  mov     rdx, rsi
0x180012e13  sbb     r9, r9
0x180012e16  and     r9, rax
0x180012e19  call    cs:__imp_EtwEventWrite
0x180012e1f  mov     r8d, edi
0x180012e22  lea     rdx, aEventUEventwri; "Event: %u, EventWrite: %d"
0x180012e29  mov     r9d, eax
0x180012e2c  lea     rcx, aSpllogevent2; "SplLogEvent2"
0x180012e33  call    ?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ; PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180012e38  mov     rcx, [rbp+60h+var_40]
0x180012e3c  xor     rcx, rsp; StackCookie
0x180012e3f  call    __security_check_cookie
0x180012e44  add     rsp, 130h
0x180012e4b  pop     r15
0x180012e4d  pop     r14
0x180012e4f  pop     r13
0x180012e51  pop     rdi
0x180012e52  pop     rsi
0x180012e53  pop     rbx
0x180012e54  pop     rbp
0x180012e55  retn
```
