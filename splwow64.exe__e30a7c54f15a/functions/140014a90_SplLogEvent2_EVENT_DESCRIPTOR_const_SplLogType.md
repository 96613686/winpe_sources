# SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)

- ea: `0x140014a90`
- end: `0x140014c2d`
- name: `?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ`
- size: `413`
- prototype: `void(const struct _EVENT_DESCRIPTOR *, struct SplLogType *, ...)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140007548`
- `0x14000f1e4`

## callees

- `0x140001ee0`
- `0x1400028b8`
- `0x140014a90`
- `0x140014c34`
- `0x140014d3c`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x140014ae5`
- `ntdll!EtwEventEnabled` at `0x140014ae5`
- `ntdll!EtwEventWrite` at `0x140014bf0`
- `ntdll!EtwEventWrite` at `0x140014bf0`

## string_xrefs

- `0x140014bf9`: `Event: %u, EventWrite: %d`

## pseudocode

```c
void SplLogEvent2(const struct _EVENT_DESCRIPTOR *a1, struct SplLogType *a2, ...)
{
  unsigned int Id; // ebx
  unsigned int v4; // esi
  unsigned int v5; // edi
  SplLogType *v6; // rdx
  int v7; // r8d
  int v8; // r9d
  va_list v9; // r15
  __int64 *v10; // rbx
  unsigned int v11; // r12d
  int v12; // edx
  __int64 *v13; // rcx
  int v14; // r8d
  __int64 v15; // rax
  unsigned int v16; // eax
  __int64 v17; // [rsp+28h] [rbp-E0h]
  SplLogType *v18; // [rsp+38h] [rbp-D0h] BYREF
  _DWORD v19[58]; // [rsp+40h] [rbp-C8h]
  _QWORD v20[28]; // [rsp+44h] [rbp-C4h]
  SplLogType *v21; // [rsp+180h] [rbp+78h]
  va_list va; // [rsp+188h] [rbp+80h] BYREF

  va_start(va, a2);
  if ( a1 )
  {
    v21 = a2;
    if ( g_bTracingEnabled )
    {
      Id = a1->Id;
      if ( (unsigned __int8)EtwEventEnabled(-1, a1) )
      {
        v4 = Id;
        memset_0(&v18, 0, 0xF0u);
        PerfLibTelemetry::WriteDbgTraceInfo("SplLogEvent2", L"Event: %u, to be written...", Id);
        if ( v21 )
        {
          v5 = 1;
          v17 = 0;
          SplLogType::TraceValue(v21, Id, 1u);
          v6 = 0;
          v7 = *((_DWORD *)v21 + 4);
          v8 = *((_DWORD *)v21 + 2);
          if ( v7 )
          {
            if ( v7 == 1 )
              v6 = *(SplLogType **)v21;
          }
          else
          {
            v6 = v21;
          }
          v18 = v6;
          va_copy(v9, va);
          v19[0] = v8;
          LODWORD(v20[0]) = 0;
          do
          {
            v9 += 8;
            v10 = (__int64 *)*((_QWORD *)v9 - 1);
            if ( !v10 )
              break;
            v11 = v5 + 1;
            SplLogType::TraceValue(*((SplLogType **)v9 - 1), v4, v5 + 1);
            v12 = *((_DWORD *)v10 + 4);
            v13 = 0;
            v14 = *((_DWORD *)v10 + 2);
            if ( v12 )
            {
              if ( v12 == 1 )
                v13 = (__int64 *)*v10;
            }
            else
            {
              v13 = v10;
            }
            v15 = v5++;
            v15 *= 2;
            *(_QWORD *)&v19[2 * v15 - 2] = v13;
            v19[2 * v15] = v14;
            LODWORD(v20[v15]) = 0;
          }
          while ( v11 < 0xF );
        }
        else
        {
          v5 = 0;
        }
        v16 = EtwEventWrite(-1, a1, v5, (unsigned __int64)&v18 & -(__int64)(v5 != 0), v17);
        PerfLibTelemetry::WriteDbgTraceInfo("SplLogEvent2", L"Event: %u, EventWrite: %d", v4, v16);
      }
    }
  }
}

```

## disassembly

```asm
0x140014a90  test    rcx, rcx
0x140014a93  jz      locret_140014C2C
0x140014a99  mov     rax, rsp
0x140014a9c  mov     [rax+10h], rdx
0x140014aa0  mov     [rax+18h], r8
0x140014aa4  mov     [rax+20h], r9
0x140014aa8  push    rbp
0x140014aa9  push    rbx
0x140014aaa  push    rsi
0x140014aab  push    rdi
0x140014aac  push    r12
0x140014aae  push    r14
0x140014ab0  push    r15
0x140014ab2  lea     rbp, [rax-68h]
0x140014ab6  sub     rsp, 130h
0x140014abd  mov     rax, cs:__security_cookie
0x140014ac4  xor     rax, rsp
0x140014ac7  mov     [rbp+60h+var_40], rax
0x140014acb  cmp     cs:?g_bTracingEnabled@@3HA, 0; int g_bTracingEnabled
0x140014ad2  mov     r14, rcx
0x140014ad5  jz      loc_140014C0F
0x140014adb  movzx   ebx, word ptr [rcx]
0x140014ade  mov     rdx, rcx
0x140014ae1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140014ae5  call    cs:__imp_EtwEventEnabled
0x140014aeb  test    al, al
0x140014aed  jz      loc_140014C0F
0x140014af3  xor     edx, edx; Val
0x140014af5  lea     rcx, [rsp+160h+var_130]; void *
0x140014afa  mov     r8d, 0F0h; Size
0x140014b00  mov     esi, ebx
0x140014b02  call    memset_0
0x140014b07  mov     r8d, ebx
0x140014b0a  lea     rdx, aEventUToBeWrit; "Event: %u, to be written..."
0x140014b11  lea     rcx, aSpllogevent2; "SplLogEvent2"
0x140014b18  call    ?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ; PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140014b1d  mov     rcx, [rbp+60h+arg_8]; this
0x140014b21  test    rcx, rcx
0x140014b24  jz      loc_140014BD5
0x140014b2a  mov     edi, 1
0x140014b2f  mov     qword ptr [rsp+20h], 0
0x140014b38  mov     r8d, edi; unsigned int
0x140014b3b  mov     edx, ebx; unsigned int
0x140014b3d  call    ?TraceValue@SplLogType@@QEAAXII@Z; SplLogType::TraceValue(uint,uint)
0x140014b42  mov     rcx, [rbp+60h+arg_8]
0x140014b46  xor     edx, edx
0x140014b48  mov     r8d, [rcx+10h]
0x140014b4c  mov     r9d, [rcx+8]
0x140014b50  test    r8d, r8d
0x140014b53  jz      short loc_140014B5F
0x140014b55  cmp     r8d, edi
0x140014b58  jnz     short loc_140014B62
0x140014b5a  mov     rdx, [rcx]
0x140014b5d  jmp     short loc_140014B62
0x140014b5f  mov     rdx, rcx
0x140014b62  mov     qword ptr [rsp+160h+var_130], rdx
0x140014b67  lea     r15, [rbp+60h+arg_10]
0x140014b6e  mov     [rsp+160h+var_128], r9d
0x140014b73  mov     [rsp+160h+var_128+4], 0
0x140014b7b  lea     r15, [r15+8]
0x140014b7f  mov     rbx, [r15-8]
0x140014b83  test    rbx, rbx
0x140014b86  jz      short loc_140014BD7
0x140014b88  lea     r12d, [rdi+1]
0x140014b8c  mov     edx, esi; unsigned int
0x140014b8e  mov     r8d, r12d; unsigned int
0x140014b91  mov     rcx, rbx; this
0x140014b94  call    ?TraceValue@SplLogType@@QEAAXII@Z; SplLogType::TraceValue(uint,uint)
0x140014b99  mov     edx, [rbx+10h]
0x140014b9c  xor     ecx, ecx
0x140014b9e  mov     r8d, [rbx+8]
0x140014ba2  test    edx, edx
0x140014ba4  jz      short loc_140014BB0
0x140014ba6  cmp     edx, 1
0x140014ba9  jnz     short loc_140014BB3
0x140014bab  mov     rcx, [rbx]
0x140014bae  jmp     short loc_140014BB3
0x140014bb0  mov     rcx, rbx
0x140014bb3  mov     eax, edi
0x140014bb5  mov     edi, r12d
0x140014bb8  add     rax, rax
0x140014bbb  mov     qword ptr [rsp+rax*8+160h+var_130], rcx
0x140014bc0  mov     [rsp+rax*8+160h+var_128], r8d
0x140014bc5  mov     [rsp+rax*8+160h+var_128+4], 0
0x140014bcd  cmp     r12d, 0Fh
0x140014bd1  jb      short loc_140014B7B
0x140014bd3  jmp     short loc_140014BD7
0x140014bd5  xor     edi, edi
0x140014bd7  mov     eax, edi
0x140014bd9  mov     r8d, edi
0x140014bdc  neg     eax
0x140014bde  mov     rdx, r14
0x140014be1  lea     rax, [rsp+160h+var_130]
0x140014be6  sbb     r9, r9
0x140014be9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140014bed  and     r9, rax
0x140014bf0  call    cs:__imp_EtwEventWrite
0x140014bf6  mov     r8d, esi
0x140014bf9  lea     rdx, aEventUEventwri; "Event: %u, EventWrite: %d"
0x140014c00  mov     r9d, eax
0x140014c03  lea     rcx, aSpllogevent2; "SplLogEvent2"
0x140014c0a  call    ?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ; PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140014c0f  mov     rcx, [rbp+60h+var_40]
0x140014c13  xor     rcx, rsp; StackCookie
0x140014c16  call    __security_check_cookie
0x140014c1b  add     rsp, 130h
0x140014c22  pop     r15
0x140014c24  pop     r14
0x140014c26  pop     r12
0x140014c28  pop     rdi
0x140014c29  pop     rsi
0x140014c2a  pop     rbx
0x140014c2b  pop     rbp
0x140014c2c  retn
```
