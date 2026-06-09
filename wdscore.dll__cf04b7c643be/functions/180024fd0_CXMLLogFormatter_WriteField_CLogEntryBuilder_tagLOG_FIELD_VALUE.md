# CXMLLogFormatter::WriteField(CLogEntryBuilder *,tagLOG_FIELD_VALUE *)

- ea: `0x180024fd0`
- end: `0x180025101`
- name: `?WriteField@CXMLLogFormatter@@CAHPEAVCLogEntryBuilder@@PEAUtagLOG_FIELD_VALUE@@@Z`
- size: `305`
- prototype: `__int64 __fastcall(struct CLogEntryBuilder *this, struct tagLOG_FIELD_VALUE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180024de0`

## callees

- `0x180023380`
- `0x18002365c`
- `0x180024fd0`
- `0x180027510`

## import_xrefs

- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18002502e`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18002502e`

## pseudocode

```c
int __fastcall CXMLLogFormatter::WriteField(struct CLogEntryBuilder *this, struct tagLOG_FIELD_VALUE *a2)
{
  int v3; // ecx
  int v5; // ecx
  int v6; // ecx
  __int64 i; // rdi
  struct _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-28h] BYREF

  v3 = *((_DWORD *)a2 + 130);
  SystemTime = 0;
  if ( !v3 )
    return CXMLLogFormatter::EscapeXML(this, *((const unsigned __int16 **)a2 + 66), 0);
  v5 = v3 - 1;
  if ( !v5 )
    return CLogEntryBuilder::Printf(this, "%d", *((_DWORD *)a2 + 132));
  v6 = v5 - 1;
  if ( v6 )
  {
    if ( v6 == 1 )
    {
      VariantTimeToSystemTime(*((DOUBLE *)a2 + 66), &SystemTime);
      return CLogEntryBuilder::Printf(
               this,
               "%d-%02d-%02dT%02d:%02d:%02d",
               SystemTime.wYear,
               SystemTime.wMonth,
               SystemTime.wDay,
               SystemTime.wHour,
               SystemTime.wMinute,
               SystemTime.wSecond);
    }
    else
    {
      return 0;
    }
  }
  else
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)a2 + 134); i = (unsigned int)(i + 1) )
    {
      if ( !CLogEntryBuilder::Printf(this, "%.2X", *(unsigned __int8 *)(*((_QWORD *)a2 + 66) + i)) )
        return 0;
    }
    return 1;
  }
}

```

## disassembly

```asm
0x180024fd0  mov     [rsp+arg_10], rbx
0x180024fd5  mov     [rsp+arg_18], rsi
0x180024fda  push    rdi
0x180024fdb  sub     rsp, 60h
0x180024fdf  mov     rax, cs:__security_cookie
0x180024fe6  xor     rax, rsp
0x180024fe9  mov     [rsp+68h+var_18], rax
0x180024fee  mov     rsi, rcx
0x180024ff1  xorps   xmm0, xmm0
0x180024ff4  mov     ecx, [rdx+208h]
0x180024ffa  mov     rbx, rdx
0x180024ffd  movups  xmmword ptr [rsp+68h+SystemTime.wYear], xmm0
0x180025002  test    ecx, ecx
0x180025004  jz      loc_1800250CF
0x18002500a  sub     ecx, 1
0x18002500d  jz      loc_1800250B7
0x180025013  sub     ecx, 1
0x180025016  jz      short loc_18002507F
0x180025018  cmp     ecx, 1
0x18002501b  jnz     loc_1800250AC
0x180025021  movsd   xmm0, qword ptr [rbx+210h]; vtime
0x180025029  lea     rdx, [rsp+68h+SystemTime]; lpSystemTime
0x18002502e  call    cs:__imp_VariantTimeToSystemTime
0x180025035  nop     dword ptr [rax+rax+00h]
0x18002503a  movzx   edx, [rsp+68h+SystemTime.wMinute]
0x18002503f  mov     rcx, rsi; this
0x180025042  movzx   eax, [rsp+68h+SystemTime.wSecond]
0x180025047  movzx   r10d, [rsp+68h+SystemTime.wHour]
0x18002504d  movzx   r11d, [rsp+68h+SystemTime.wDay]
0x180025053  movzx   r9d, [rsp+68h+SystemTime.wMonth]
0x180025059  movzx   r8d, [rsp+68h+SystemTime.wYear]
0x18002505f  mov     [rsp+68h+var_30], eax
0x180025063  mov     [rsp+68h+var_38], edx
0x180025067  lea     rdx, aD02d02dt02d02d; "%d-%02d-%02dT%02d:%02d:%02d"
0x18002506e  mov     [rsp+68h+var_40], r10d
0x180025073  mov     [rsp+68h+var_48], r11d
0x180025078  call    ?Printf@CLogEntryBuilder@@QEAAHPEBDZZ; CLogEntryBuilder::Printf(char const *,...)
0x18002507d  jmp     short loc_1800250E1
0x18002507f  xor     edi, edi
0x180025081  cmp     edi, [rbx+218h]
0x180025087  jnb     short loc_1800250B0
0x180025089  mov     rax, [rbx+210h]
0x180025090  lea     rdx, a2x; "%.2X"
0x180025097  mov     rcx, rsi; this
0x18002509a  movzx   r8d, byte ptr [rax+rdi]
0x18002509f  call    ?Printf@CLogEntryBuilder@@QEAAHPEBDZZ; CLogEntryBuilder::Printf(char const *,...)
0x1800250a4  test    eax, eax
0x1800250a6  jz      short loc_1800250AC
0x1800250a8  inc     edi
0x1800250aa  jmp     short loc_180025081
0x1800250ac  xor     eax, eax
0x1800250ae  jmp     short loc_1800250E1
0x1800250b0  mov     eax, 1
0x1800250b5  jmp     short loc_1800250E1
0x1800250b7  mov     r8d, [rdx+210h]
0x1800250be  mov     rcx, rsi; this
0x1800250c1  lea     rdx, aD_0; "%d"
0x1800250c8  call    ?Printf@CLogEntryBuilder@@QEAAHPEBDZZ; CLogEntryBuilder::Printf(char const *,...)
0x1800250cd  jmp     short loc_1800250E1
0x1800250cf  mov     rdx, [rdx+210h]; unsigned __int16 *
0x1800250d6  xor     r8d, r8d; unsigned int *
0x1800250d9  mov     rcx, rsi; this
0x1800250dc  call    ?EscapeXML@CXMLLogFormatter@@CAHPEAVCLogEntryBuilder@@PEBGPEAI@Z; CXMLLogFormatter::EscapeXML(CLogEntryBuilder *,ushort const *,uint *)
0x1800250e1  mov     rcx, [rsp+68h+var_18]
0x1800250e6  xor     rcx, rsp; StackCookie
0x1800250e9  call    __security_check_cookie
0x1800250ee  lea     r11, [rsp+68h+var_8]
0x1800250f3  mov     rbx, [r11+20h]
0x1800250f7  mov     rsi, [r11+28h]
0x1800250fb  mov     rsp, r11
0x1800250fe  pop     rdi
0x1800250ff  retn
```
