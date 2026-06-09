# CActivityID::getCurrentCActivityID(CActivityID * const)

- ea: `0x383881c10`
- end: `0x383881d4e`
- name: `?getCurrentCActivityID@CActivityID@@SAHQEAU1@@Z`
- size: `318`
- prototype: `__int64 __fastcall(UUID *Uuid)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x3838436a0`
- `0x38387e400`
- `0x383a9f290`

## callees

- `0x3838434c0`
- `0x383881c10`
- `0x38391ac10`
- `0x38391aed0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383890d93`
- `KERNEL32!GetLastError` at `0x3838f563d`
- `KERNEL32!GetLastError` at `0x383890d93`
- `KERNEL32!GetLastError` at `0x3838f563d`
- `KERNEL32!TlsGetValue` at `0x383881cff`
- `KERNEL32!TlsGetValue` at `0x383881cff`
- `KERNEL32!TlsSetValue` at `0x383890e36`
- `KERNEL32!TlsSetValue` at `0x383890e36`
- `RPCRT4!UuidCreate` at `0x383890e06`
- `RPCRT4!UuidCreate` at `0x383890e06`

## pseudocode

```c
__int64 __fastcall CActivityID::getCurrentCActivityID(UUID *Uuid)
{
  unsigned int Value; // eax
  __int64 (*v4)(void); // rsi
  unsigned int v5; // edi
  DWORD LastError; // eax
  bool v7; // cf
  int v8; // eax
  DWORD v9; // ecx
  DWORD v10; // eax
  GUID v11; // [rsp+30h] [rbp-28h] BYREF

  if ( !g_pfnEventActivityIdControl )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B4A288[0] && bidID != -1 )
      off_383B15040();
    return 0;
  }
  if ( g_dwCorrelationIndex != -1 )
  {
    Value = (unsigned int)TlsGetValue(g_dwCorrelationIndex);
    v4 = g_pfnEventActivityIdControl;
    v5 = Value;
    if ( Value )
    {
      if ( !(unsigned int)g_pfnEventActivityIdControl() )
      {
        Uuid[1].Data1 = v5;
        return 1;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( (bidGblFlags & 2) != 0 && off_383B4A278[0] )
        {
          bidTraceW(off_383B43538[0], 1959936, off_383B4A278[0], LastError);
          return 0;
        }
        return 0;
      }
      v11 = GUID_NULL;
      ((void (__fastcall *)(__int64, GUID *))v4)(1, &v11);
      v7 = *(_QWORD *)&v11.Data1 < *(_QWORD *)&GUID_NULL.Data1;
      if ( *(_QWORD *)&v11.Data1 == *(_QWORD *)&GUID_NULL.Data1
        && (v7 = *(_QWORD *)v11.Data4 < *(_QWORD *)GUID_NULL.Data4, *(_QWORD *)v11.Data4 == *(_QWORD *)GUID_NULL.Data4) )
      {
        v8 = 0;
      }
      else
      {
        v8 = -v7 - (v7 - 1);
      }
      if ( v8 || !UuidCreate(Uuid) && !((unsigned int (__fastcall *)(__int64, UUID *))v4)(2, Uuid) )
      {
        v9 = g_dwCorrelationIndex;
        Uuid[1].Data1 = 1;
        if ( TlsSetValue(v9, (LPVOID)1) )
          return 1;
      }
    }
    v10 = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_383B4A270[0] )
      bidTraceW(off_383B43538[0], 1995776, off_383B4A270[0], v10);
    return 0;
  }
  if ( (bidGblFlags & 2) == 0 || !off_383B4A280[0] || bidID == -1 )
    return 0;
  off_383B15040();
  return 0;
}

```

## disassembly

```asm
0x383881c10  push    rbx
0x383881c12  sub     rsp, 50h
0x383881c16  mov     rax, cs:__security_cookie
0x383881c1d  xor     rax, rsp
0x383881c20  mov     [rsp+58h+var_18], rax
0x383881c25  cmp     cs:?g_pfnEventActivityIdControl@@3P6A_JXZEA, 0; __int64 (*g_pfnEventActivityIdControl)(void)
0x383881c2d  mov     rbx, rcx
0x383881c30  jnz     short loc_383881C8E
0x383881c32  test    byte ptr cs:_bidGblFlags, 2
0x383881c39  jz      short loc_383881C79
0x383881c3b  mov     rax, cs:off_383B4A288; "<CActivityID::getCurrentCActivityID|ERR"...
0x383881c42  test    rax, rax
0x383881c45  jz      short loc_383881C79
0x383881c47  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383881c4f  jz      short loc_383881C79
0x383881c51  mov     r9, cs:off_383B4A288; "<CActivityID::getCurrentCActivityID|ERR"...
0x383881c58  mov     rdx, cs:off_383B43538; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383881c5f  mov     rcx, cs:_bidID
0x383881c66  xor     eax, eax
0x383881c68  mov     r8d, 1DA000h
0x383881c6e  mov     [rsp+58h+var_38], rax
0x383881c73  call    cs:off_383B15040
0x383881c79  xor     eax, eax
0x383881c7b  mov     rcx, [rsp+58h+var_18]
0x383881c80  xor     rcx, rsp; StackCookie
0x383881c83  call    __security_check_cookie
0x383881c88  add     rsp, 50h
0x383881c8c  pop     rbx
0x383881c8d  retn
0x383881c8e  mov     ecx, cs:?g_dwCorrelationIndex@@3KA; dwTlsIndex
0x383881c94  cmp     ecx, 0FFFFFFFFh
0x383881c97  jnz     short loc_383881CF5
0x383881c99  test    byte ptr cs:_bidGblFlags, 2
0x383881ca0  jz      short loc_383881C79
0x383881ca2  mov     rax, cs:off_383B4A280; "<CActivityID::getCurrentCActivityID|ERR"...
0x383881ca9  test    rax, rax
0x383881cac  jz      short loc_383881C79
0x383881cae  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383881cb6  jz      short loc_383881C79
0x383881cb8  mov     r9, cs:off_383B4A280; "<CActivityID::getCurrentCActivityID|ERR"...
0x383881cbf  mov     rdx, cs:off_383B43538; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383881cc6  mov     rcx, cs:_bidID
0x383881ccd  xor     eax, eax
0x383881ccf  mov     r8d, 1DB800h
0x383881cd5  mov     [rsp+58h+var_38], rax
0x383881cda  call    cs:off_383B15040
0x383881ce0  xor     eax, eax
0x383881ce2  mov     rcx, [rsp+58h+var_18]
0x383881ce7  xor     rcx, rsp; StackCookie
0x383881cea  call    __security_check_cookie
0x383881cef  add     rsp, 50h
0x383881cf3  pop     rbx
0x383881cf4  retn
0x383881cf5  mov     [rsp+58h+arg_8], rsi
0x383881cfa  mov     [rsp+58h+arg_10], rdi
0x383881cff  call    cs:__imp_TlsGetValue
0x383881d05  mov     rsi, cs:?g_pfnEventActivityIdControl@@3P6A_JXZEA; __int64 (*g_pfnEventActivityIdControl)(void)
0x383881d0c  mov     rdi, rax
0x383881d0f  test    eax, eax
0x383881d11  jz      loc_383890D93
0x383881d17  mov     rdx, rbx
0x383881d1a  mov     ecx, 1
0x383881d1f  call    rsi ; __int64 (*g_pfnEventActivityIdControl)(void)
0x383881d21  test    eax, eax
0x383881d23  jnz     loc_3838F563D
0x383881d29  mov     [rbx+10h], edi
0x383881d2c  mov     eax, 1
0x383881d31  mov     rsi, [rsp+58h+arg_8]
0x383881d36  mov     rdi, [rsp+58h+arg_10]
0x383881d3b  mov     rcx, [rsp+58h+var_18]
0x383881d40  xor     rcx, rsp; StackCookie
0x383881d43  call    __security_check_cookie
0x383881d48  add     rsp, 50h
0x383881d4c  pop     rbx
0x383881d4d  retn
0x383890d93  call    cs:__imp_GetLastError
0x383890d99  test    eax, eax
0x383890d9b  jnz     loc_3838F55FC
0x383890da1  mov     eax, cs:GUID_NULL.Data1
0x383890da7  lea     rdx, [rsp+58h+var_28]
0x383890dac  mov     ecx, 1
0x383890db1  mov     dword ptr [rsp+58h+var_28], eax
0x383890db5  mov     eax, dword ptr cs:GUID_NULL.Data2
0x383890dbb  mov     dword ptr [rsp+58h+var_28+4], eax
0x383890dbf  mov     eax, dword ptr cs:GUID_NULL.Data4
0x383890dc5  mov     [rsp+58h+var_20], eax
0x383890dc9  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x383890dcf  mov     [rsp+58h+var_1C], eax
0x383890dd3  call    rsi ; __int64 (*g_pfnEventActivityIdControl)(void)
0x383890dd5  lea     r11, [rsp+58h+var_28]
0x383890dda  mov     rcx, [r11]
0x383890ddd  lea     rax, GUID_NULL
0x383890de4  cmp     rcx, [rax]
0x383890de7  jnz     loc_3838F5633
0x383890ded  mov     rcx, [r11+8]
0x383890df1  cmp     rcx, [rax+8]
0x383890df5  jnz     loc_3838F5633
0x383890dfb  xor     eax, eax
0x383890dfd  jmp     short $+2
0x383890dff  test    eax, eax
0x383890e01  jnz     short loc_383890E24
0x383890e03  mov     rcx, rbx; Uuid
0x383890e06  call    cs:__imp_UuidCreate
0x383890e0c  test    eax, eax
0x383890e0e  jnz     loc_3838F563D
0x383890e14  lea     ecx, [rax+2]
0x383890e17  mov     rdx, rbx
0x383890e1a  call    rsi ; __int64 (*g_pfnEventActivityIdControl)(void)
0x383890e1c  test    eax, eax
0x383890e1e  jnz     loc_3838F563D
0x383890e24  mov     ecx, cs:?g_dwCorrelationIndex@@3KA; dwTlsIndex
0x383890e2a  mov     edx, 1; lpTlsValue
0x383890e2f  mov     dword ptr [rbx+10h], 1
0x383890e36  call    cs:__imp_TlsSetValue
0x383890e3c  test    eax, eax
0x383890e3e  jz      loc_3838F563D
0x383890e44  jmp     loc_383881D2C
0x3838f55fc  test    byte ptr cs:_bidGblFlags, 2
0x3838f5603  jz      short loc_3838F5673
0x3838f5605  mov     rcx, cs:off_383B4A278; "<CActivityID::getCurrentCActivityID|ERR"...
0x3838f560c  test    rcx, rcx
0x3838f560f  jz      short loc_3838F5673
0x3838f5611  mov     r8, cs:off_383B4A278; "<CActivityID::getCurrentCActivityID|ERR"...
0x3838f5618  mov     rcx, cs:off_383B43538; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838f561f  mov     r9d, eax
0x3838f5622  mov     edx, 1DE800h
0x3838f5627  call    _bidTraceW
0x3838f562c  xor     eax, eax
0x3838f562e  jmp     loc_383881D31
0x3838f5633  sbb     eax, eax
0x3838f5635  sbb     eax, 0FFFFFFFFh
0x3838f5638  jmp     loc_383890DFF
0x3838f563d  call    cs:__imp_GetLastError
0x3838f5643  test    byte ptr cs:_bidGblFlags, 2
0x3838f564a  jz      short loc_3838F5673
0x3838f564c  mov     rcx, cs:off_383B4A270; "<CActivityID::getCurrentCActivityID|ERR"...
0x3838f5653  test    rcx, rcx
0x3838f5656  jz      short loc_3838F5673
0x3838f5658  mov     r8, cs:off_383B4A270; "<CActivityID::getCurrentCActivityID|ERR"...
0x3838f565f  mov     rcx, cs:off_383B43538; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838f5666  mov     r9d, eax
0x3838f5669  mov     edx, 1E7400h
0x3838f566e  call    _bidTraceW
0x3838f5673  xor     eax, eax
0x3838f5675  jmp     loc_383881D31
```
