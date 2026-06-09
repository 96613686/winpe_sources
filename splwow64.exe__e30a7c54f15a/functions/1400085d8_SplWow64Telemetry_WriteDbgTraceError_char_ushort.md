# SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)

- ea: `0x1400085d8`
- end: `0x1400086da`
- name: `?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ`
- size: `258`
- prototype: `void(char *, unsigned __int16 *, ...)`
- caller_count: `29`
- callee_count: `7`
- tags: ``

## callers

- `0x140006f98`
- `0x1400077fc`
- `0x140007dac`
- `0x14000805c`
- `0x1400083f4`
- `0x14000cca0`
- `0x14000d264`
- `0x14000d420`
- `0x14000d6c0`
- `0x14000d9e0`
- `0x14000ddd0`
- `0x14000dfe0`
- `0x14000e110`
- `0x14000e290`
- `0x14000e3c0`
- `0x14000e530`
- `0x14000e6a0`
- `0x14000ed78`
- `0x14000ef6c`
- `0x14000f42c`
- `0x14000f5c4`
- `0x14000fae0`
- `0x140010400`
- `0x1400112f4`
- `0x140011624`
- `0x140011814`
- `0x140011bb0`
- `0x14001200c`
- `0x140012390`

## callees

- `0x1400016dc`
- `0x140001ee0`
- `0x1400028c4`
- `0x140004d0c`
- `0x1400072d0`
- `0x1400085d8`
- `0x1400154e0`

## pseudocode

```c
void SplWow64Telemetry::WriteDbgTraceError(char *a1, unsigned __int16 *a2, ...)
{
  _DWORD *v3; // rax
  unsigned int v4; // eax
  _DWORD *v5; // rax
  _DWORD *v6; // rcx
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
  v3 = (_DWORD *)*((_QWORD *)SplWow64Telemetry::Instance() + 1);
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
        v5 = (_DWORD *)*((_QWORD *)SplWow64Telemetry::Instance() + 1);
        if ( v5 && *v5 )
        {
          SplWow64Telemetry::Instance();
          v6 = (_DWORD *)*((_QWORD *)SplWow64Logging::Instance() + 1);
          if ( *v6 > 2u )
          {
            v9 = a1;
            v10 = Buffer;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v6,
              (unsigned int)word_14001D0EA,
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
0x1400085d8  mov     rax, rsp
0x1400085db  mov     [rax+10h], rdx
0x1400085df  mov     [rax+18h], r8
0x1400085e3  mov     [rax+20h], r9
0x1400085e7  push    rbp
0x1400085e8  push    rbx
0x1400085e9  lea     rbp, [rax-1F68h]
0x1400085f0  mov     eax, 2058h
0x1400085f5  call    _alloca_probe
0x1400085fa  sub     rsp, rax
0x1400085fd  mov     rax, cs:__security_cookie
0x140008604  xor     rax, rsp
0x140008607  mov     [rbp+1F60h+var_20], rax
0x14000860e  mov     rbx, rcx
0x140008611  call    ?Instance@SplWow64Telemetry@@KAPEAV1@XZ; SplWow64Telemetry::Instance(void)
0x140008616  mov     rax, [rax+8]
0x14000861a  test    rax, rax
0x14000861d  jz      loc_1400086C1
0x140008623  mov     eax, [rax]
0x140008625  test    eax, eax
0x140008627  jz      loc_1400086C1
0x14000862d  mov     r8, [rbp+1F60h+Format]; Format
0x140008634  lea     r9, [rbp+1F60h+Args]; Args
0x14000863b  mov     edx, 0FFFh; BufferCount
0x140008640  mov     [rsp+2060h+var_2030], 0
0x140008649  lea     rcx, [rsp+2060h+Buffer]; Buffer
0x14000864e  call    _vsnwprintf
0x140008653  test    eax, eax
0x140008655  js      short loc_1400086C1
0x140008657  cmp     eax, 0FFFh
0x14000865c  ja      short loc_1400086C1
0x14000865e  jnz     short loc_140008669
0x140008660  xor     eax, eax
0x140008662  mov     [rbp+1F60h+var_22], ax
0x140008669  call    ?Instance@SplWow64Telemetry@@KAPEAV1@XZ; SplWow64Telemetry::Instance(void)
0x14000866e  mov     rax, [rax+8]
0x140008672  test    rax, rax
0x140008675  jz      short loc_1400086C1
0x140008677  mov     eax, [rax]
0x140008679  test    eax, eax
0x14000867b  jz      short loc_1400086C1
0x14000867d  call    ?Instance@SplWow64Telemetry@@KAPEAV1@XZ; SplWow64Telemetry::Instance(void)
0x140008682  call    ?Instance@SplWow64Logging@@KAPEAV1@XZ; SplWow64Logging::Instance(void)
0x140008687  mov     rcx, [rax+8]
0x14000868b  mov     eax, [rcx]
0x14000868d  cmp     eax, 2
0x140008690  jbe     short loc_1400086C1
0x140008692  lea     rax, [rsp+2060h+Buffer]
0x140008697  mov     [rsp+2060h+var_2030], rbx
0x14000869c  mov     [rsp+2060h+var_2028], rax
0x1400086a1  lea     rdx, word_14001D0EA
0x1400086a8  lea     rax, [rsp+2060h+var_2028]
0x1400086ad  mov     [rsp+2060h+var_2038], rax
0x1400086b2  lea     rax, [rsp+2060h+var_2030]
0x1400086b7  mov     [rsp+2060h+var_2040], rax
0x1400086bc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1400086c1  mov     rcx, [rbp+1F60h+var_20]
0x1400086c8  xor     rcx, rsp; StackCookie
0x1400086cb  call    __security_check_cookie
0x1400086d0  add     rsp, 2058h
0x1400086d7  pop     rbx
0x1400086d8  pop     rbp
0x1400086d9  retn
```
