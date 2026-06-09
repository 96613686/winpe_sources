# SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)

- ea: `0x1400086e0`
- end: `0x1400087e2`
- name: `?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ`
- size: `258`
- prototype: `void(char *, unsigned __int16 *, ...)`
- caller_count: `26`
- callee_count: `7`
- tags: ``

## callers

- `0x140006eb0`
- `0x140006f20`
- `0x140007790`
- `0x140007d00`
- `0x140007dac`
- `0x14000805c`
- `0x1400082e0`
- `0x1400083f4`
- `0x14000cca0`
- `0x14000d920`
- `0x14000d9e0`
- `0x14000dc10`
- `0x14000ddd0`
- `0x14000df00`
- `0x14000dfe0`
- `0x14000e110`
- `0x14000e290`
- `0x14000e3c0`
- `0x14000e530`
- `0x14000e6a0`
- `0x14000fae0`
- `0x14000fec0`
- `0x140011624`
- `0x140011814`
- `0x140011bb0`
- `0x140012740`

## callees

- `0x1400016dc`
- `0x140001ee0`
- `0x1400028c4`
- `0x140004d0c`
- `0x1400072d0`
- `0x1400086e0`
- `0x1400154e0`

## pseudocode

```c
void SplWow64Telemetry::WriteDbgTraceInfo(char *a1, unsigned __int16 *a2, ...)
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
          if ( *v6 > 4u )
          {
            v9 = a1;
            v10 = Buffer;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v6,
              (unsigned int)word_14001D112,
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
0x1400086e0  mov     rax, rsp
0x1400086e3  mov     [rax+10h], rdx
0x1400086e7  mov     [rax+18h], r8
0x1400086eb  mov     [rax+20h], r9
0x1400086ef  push    rbp
0x1400086f0  push    rbx
0x1400086f1  lea     rbp, [rax-1F68h]
0x1400086f8  mov     eax, 2058h
0x1400086fd  call    _alloca_probe
0x140008702  sub     rsp, rax
0x140008705  mov     rax, cs:__security_cookie
0x14000870c  xor     rax, rsp
0x14000870f  mov     [rbp+1F60h+var_20], rax
0x140008716  mov     rbx, rcx
0x140008719  call    ?Instance@SplWow64Telemetry@@KAPEAV1@XZ; SplWow64Telemetry::Instance(void)
0x14000871e  mov     rax, [rax+8]
0x140008722  test    rax, rax
0x140008725  jz      loc_1400087C9
0x14000872b  mov     eax, [rax]
0x14000872d  test    eax, eax
0x14000872f  jz      loc_1400087C9
0x140008735  mov     r8, [rbp+1F60h+Format]; Format
0x14000873c  lea     r9, [rbp+1F60h+Args]; Args
0x140008743  mov     edx, 0FFFh; BufferCount
0x140008748  mov     [rsp+2060h+var_2030], 0
0x140008751  lea     rcx, [rsp+2060h+Buffer]; Buffer
0x140008756  call    _vsnwprintf
0x14000875b  test    eax, eax
0x14000875d  js      short loc_1400087C9
0x14000875f  cmp     eax, 0FFFh
0x140008764  ja      short loc_1400087C9
0x140008766  jnz     short loc_140008771
0x140008768  xor     eax, eax
0x14000876a  mov     [rbp+1F60h+var_22], ax
0x140008771  call    ?Instance@SplWow64Telemetry@@KAPEAV1@XZ; SplWow64Telemetry::Instance(void)
0x140008776  mov     rax, [rax+8]
0x14000877a  test    rax, rax
0x14000877d  jz      short loc_1400087C9
0x14000877f  mov     eax, [rax]
0x140008781  test    eax, eax
0x140008783  jz      short loc_1400087C9
0x140008785  call    ?Instance@SplWow64Telemetry@@KAPEAV1@XZ; SplWow64Telemetry::Instance(void)
0x14000878a  call    ?Instance@SplWow64Logging@@KAPEAV1@XZ; SplWow64Logging::Instance(void)
0x14000878f  mov     rcx, [rax+8]
0x140008793  mov     eax, [rcx]
0x140008795  cmp     eax, 4
0x140008798  jbe     short loc_1400087C9
0x14000879a  lea     rax, [rsp+2060h+Buffer]
0x14000879f  mov     [rsp+2060h+var_2030], rbx
0x1400087a4  mov     [rsp+2060h+var_2028], rax
0x1400087a9  lea     rdx, word_14001D112
0x1400087b0  lea     rax, [rsp+2060h+var_2028]
0x1400087b5  mov     [rsp+2060h+var_2038], rax
0x1400087ba  lea     rax, [rsp+2060h+var_2030]
0x1400087bf  mov     [rsp+2060h+var_2040], rax
0x1400087c4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1400087c9  mov     rcx, [rbp+1F60h+var_20]
0x1400087d0  xor     rcx, rsp; StackCookie
0x1400087d3  call    __security_check_cookie
0x1400087d8  add     rsp, 2058h
0x1400087df  pop     rbx
0x1400087e0  pop     rbp
0x1400087e1  retn
```
