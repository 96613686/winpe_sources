# PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)

- ea: `0x140014c34`
- end: `0x140014d35`
- name: `?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ`
- size: `257`
- prototype: `void(char *, unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140014a90`
- `0x140014d3c`

## callees

- `0x1400016dc`
- `0x140001ee0`
- `0x1400028c4`
- `0x1400148f8`
- `0x1400149d0`
- `0x140014c34`
- `0x1400154e0`

## pseudocode

```c
void PerfLibTelemetry::WriteDbgTraceInfo(char *a1, unsigned __int16 *a2, ...)
{
  _DWORD *v3; // rax
  unsigned int v4; // eax
  _DWORD *v5; // rax
  const struct _tlgProvider_t *v6; // rax
  int v7; // r8d
  int v8; // r9d
  char *v9; // [rsp+38h] [rbp-D0h] BYREF
  wchar_t *v10; // [rsp+40h] [rbp-C8h] BYREF
  wchar_t Buffer[4096]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 Args; // [rsp+2088h] [rbp+1F80h] BYREF
  va_list Argsa; // [rsp+2088h] [rbp+1F80h]
  __int64 v15; // [rsp+2090h] [rbp+1F88h]
  va_list va1; // [rsp+2098h] [rbp+1F90h] BYREF

  va_start(va1, a2);
  va_start(Argsa, a2);
  Args = va_arg(va1, _QWORD);
  v15 = va_arg(va1, _QWORD);
  v3 = (_DWORD *)*((_QWORD *)PerfLibTelemetry::Instance() + 1);
  if ( v3 )
  {
    if ( *v3 )
    {
      v9 = 0;
      v4 = vsnwprintf(Buffer, 0xFFFu, a2, Argsa);
      if ( v4 < 0x1000 )
      {
        if ( v4 == 4095 )
          Buffer[4095] = 0;
        v5 = (_DWORD *)*((_QWORD *)PerfLibTelemetry::Instance() + 1);
        if ( v5 && *v5 )
        {
          PerfLibTelemetry::Instance();
          v6 = PerfLibLogging::Provider();
          if ( *(_DWORD *)v6 > 4u )
          {
            v9 = a1;
            v10 = Buffer;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v6,
              (unsigned int)byte_14001D139,
              v7,
              v8,
              (__int64)&v9,
              (__int64)&v10);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140014c34  mov     rax, rsp
0x140014c37  mov     [rax+10h], rdx
0x140014c3b  mov     [rax+18h], r8
0x140014c3f  mov     [rax+20h], r9
0x140014c43  push    rbp
0x140014c44  push    rbx
0x140014c45  lea     rbp, [rax-1F68h]
0x140014c4c  mov     eax, 2058h
0x140014c51  call    _alloca_probe
0x140014c56  sub     rsp, rax
0x140014c59  mov     rax, cs:__security_cookie
0x140014c60  xor     rax, rsp
0x140014c63  mov     [rbp+1F60h+var_20], rax
0x140014c6a  mov     rbx, rcx
0x140014c6d  call    ?Instance@PerfLibTelemetry@@KAPEAV1@XZ; PerfLibTelemetry::Instance(void)
0x140014c72  mov     rax, [rax+8]
0x140014c76  test    rax, rax
0x140014c79  jz      loc_140014D1C
0x140014c7f  mov     eax, [rax]
0x140014c81  test    eax, eax
0x140014c83  jz      loc_140014D1C
0x140014c89  mov     r8, [rbp+1F60h+Format]; Format
0x140014c90  lea     r9, [rbp+1F60h+Args]; Args
0x140014c97  mov     edx, 0FFFh; BufferCount
0x140014c9c  mov     [rsp+2060h+var_2030], 0
0x140014ca5  lea     rcx, [rsp+2060h+Buffer]; Buffer
0x140014caa  call    _vsnwprintf
0x140014caf  test    eax, eax
0x140014cb1  js      short loc_140014D1C
0x140014cb3  cmp     eax, 0FFFh
0x140014cb8  ja      short loc_140014D1C
0x140014cba  jnz     short loc_140014CC5
0x140014cbc  xor     eax, eax
0x140014cbe  mov     [rbp+1F60h+var_22], ax
0x140014cc5  call    ?Instance@PerfLibTelemetry@@KAPEAV1@XZ; PerfLibTelemetry::Instance(void)
0x140014cca  mov     rax, [rax+8]
0x140014cce  test    rax, rax
0x140014cd1  jz      short loc_140014D1C
0x140014cd3  mov     eax, [rax]
0x140014cd5  test    eax, eax
0x140014cd7  jz      short loc_140014D1C
0x140014cd9  call    ?Instance@PerfLibTelemetry@@KAPEAV1@XZ; PerfLibTelemetry::Instance(void)
0x140014cde  call    ?Provider@PerfLibLogging@@SAPEBU_tlgProvider_t@@XZ; PerfLibLogging::Provider(void)
0x140014ce3  mov     ecx, [rax]
0x140014ce5  cmp     ecx, 4
0x140014ce8  jbe     short loc_140014D1C
0x140014cea  lea     rcx, [rsp+2060h+Buffer]
0x140014cef  mov     [rsp+2060h+var_2030], rbx
0x140014cf4  mov     [rsp+2060h+var_2028], rcx
0x140014cf9  lea     rdx, byte_14001D139
0x140014d00  lea     rcx, [rsp+2060h+var_2028]
0x140014d05  mov     [rsp+2060h+var_2038], rcx
0x140014d0a  lea     rcx, [rsp+2060h+var_2030]
0x140014d0f  mov     [rsp+2060h+var_2040], rcx
0x140014d14  mov     rcx, rax
0x140014d17  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140014d1c  mov     rcx, [rbp+1F60h+var_20]
0x140014d23  xor     rcx, rsp; StackCookie
0x140014d26  call    __security_check_cookie
0x140014d2b  add     rsp, 2058h
0x140014d32  pop     rbx
0x140014d33  pop     rbp
0x140014d34  retn
```
