# CVssFunctionTracer::GetCurrentContexts(void)

- ea: `0x180034f3c`
- end: `0x180035190`
- name: `?GetCurrentContexts@CVssFunctionTracer@@QEAAPEAGXZ`
- size: `596`
- prototype: `unsigned __int16 *__fastcall(CVssFunctionTracer *__hidden this)`
- caller_count: `3`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800358f4`
- `0x18003649c`
- `0x180036614`

## callees

- `0x180001580`
- `0x1800015a4`
- `0x18000212c`
- `0x180002630`
- `0x18002e79c`
- `0x1800333c4`
- `0x1800336cc`
- `0x180034ba4`
- `0x180034e64`
- `0x180034f3c`
- `0x1800356fc`
- `0x18003649c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003515c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003515c`

## pseudocode

```c
unsigned __int16 *__fastcall CVssFunctionTracer::GetCurrentContexts(CVssFunctionTracer *this)
{
  CVssFunctionTracer *j; // rdi
  int i; // ebx
  int k; // ebx
  __int64 v5; // rcx
  __int64 StringW; // rax
  const unsigned __int16 *v7; // rdx
  LPVOID v9; // [rsp+30h] [rbp-118h] BYREF
  int v10; // [rsp+38h] [rbp-110h] BYREF
  _QWORD v11[5]; // [rsp+48h] [rbp-100h] BYREF
  _QWORD v12[2]; // [rsp+70h] [rbp-D8h] BYREF
  const unsigned __int16 *v13; // [rsp+80h] [rbp-C8h]
  __int64 v14; // [rsp+88h] [rbp-C0h]
  int v15; // [rsp+90h] [rbp-B8h]
  _BYTE v16[120]; // [rsp+98h] [rbp-B0h] BYREF
  int v17; // [rsp+110h] [rbp-38h]

  v9 = 0;
  if ( !CVssAutoCoString::CopyFrom(&v9, &qword_180050E70) )
  {
    v12[0] = L"base\\stor\\vss\\modules\\trace\\fntracer.cpp";
    v12[1] = L"CVssFunctionTracer::GetCurrentContexts";
    v13 = L"TRCTRCC";
    v14 = 0xB0000037BLL;
    v15 = 255;
    v17 = 0x1000000;
    memset_0(v16, 0, sizeof(v16));
    CVssFunctionTracer::Throw(this, v12, 2147942414LL, L"internal tracing buffer - out of memory");
  }
  try
  {
    `eh vector constructor iterator'(v12, 0x20u, 4u, std::wstring::wstring, std::wstring::~wstring);
    for ( i = 0; i < 4; ++i )
    {
      for ( j = this; j; j = (CVssFunctionTracer *)*((_QWORD *)j + 12) )
      {
        if ( *((_QWORD *)j + i + 8) )
        {
          std::wstring::wstring(v11);
          std::wstring::_Append<unsigned short>(&v12[4 * i]);
          std::wstring::_Tidy_deallocate(v11);
        }
      }
    }
    for ( k = 0; k < 4; ++k )
    {
      if ( (&v13)[4 * k] )
      {
        CVssAutoCoString::Append((CVssAutoCoString *)&v9, L"\n\n");
        v5 = (unsigned int)k;
        if ( k )
        {
          v5 = (unsigned int)(k - 1);
          if ( k != 1 )
            v5 = (unsigned int)(k - 2);
        }
        StringW = CVssResource::LoadStringW(v5, v11);
        if ( *(_QWORD *)(StringW + 24) > 7u )
          StringW = *(_QWORD *)StringW;
        CVssAutoCoString::Append((CVssAutoCoString *)&v9, (const unsigned __int16 *)StringW);
        std::wstring::_Tidy_deallocate(v11);
        v7 = (const unsigned __int16 *)&v12[4 * k];
        if ( (unsigned __int64)*(&v14 + 4 * k) > 7 )
          v7 = *(const unsigned __int16 **)v7;
        CVssAutoCoString::Append((CVssAutoCoString *)&v9, v7);
      }
    }
  }
  catch ( std::bad_alloc )
  {
    v10 = -2147024882;
    throw (long *)&v10;
  }
  `eh vector constructor iterator'(v12, 0x20u, 4u, std::wstring::wstring, std::wstring::~wstring);
  for ( i = 0; i < 4; ++i )
  {
    for ( j = this; j; j = (CVssFunctionTracer *)*((_QWORD *)j + 12) )
    {
      if ( *((_QWORD *)j + i + 8) )
      {
        std::wstring::wstring(v11);
        std::wstring::_Append<unsigned short>(&v12[4 * i]);
        std::wstring::_Tidy_deallocate(v11);
      }
    }
  }
  for ( k = 0; k < 4; ++k )
  {
    if ( (&v13)[4 * k] )
    {
      CVssAutoCoString::Append((CVssAutoCoString *)&v9, L"\n\n");
      v5 = (unsigned int)k;
      if ( k )
      {
        v5 = (unsigned int)(k - 1);
        if ( k != 1 )
          v5 = (unsigned int)(k - 2);
      }
      StringW = CVssResource::LoadStringW(v5, v11);
      if ( *(_QWORD *)(StringW + 24) > 7u )
        StringW = *(_QWORD *)StringW;
      CVssAutoCoString::Append((CVssAutoCoString *)&v9, (const unsigned __int16 *)StringW);
      std::wstring::_Tidy_deallocate(v11);
      v7 = (const unsigned __int16 *)&v12[4 * k];
      if ( (unsigned __int64)*(&v14 + 4 * k) > 7 )
        v7 = *(const unsigned __int16 **)v7;
      CVssAutoCoString::Append((CVssAutoCoString *)&v9, v7);
    }
  }
}

```

## disassembly

```asm
0x180034f3c  mov     [rsp+arg_8], rbx
0x180034f41  mov     [rsp+arg_10], rsi
0x180034f46  push    rdi
0x180034f47  push    r13
0x180034f49  push    r14
0x180034f4b  sub     rsp, 130h
0x180034f52  mov     rax, cs:__security_cookie
0x180034f59  xor     rax, rsp
0x180034f5c  mov     [rsp+148h+var_28], rax
0x180034f64  mov     r14, rcx
0x180034f67  mov     [rsp+148h+var_118], 0
0x180034f70  lea     rdx, qword_180050E70; unsigned __int16 *
0x180034f77  lea     rcx, [rsp+148h+var_118]; this
0x180034f7c  call    ?CopyFrom@CVssAutoCoString@@QEAA_NPEBG@Z; CVssAutoCoString::CopyFrom(ushort const *)
0x180034f81  test    al, al
0x180034f83  jnz     loc_18003500A
0x180034f89  lea     rax, aBaseStorVssMod_0; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x180034f90  mov     [rsp+148h+var_D8], rax
0x180034f95  lea     rax, aCvssfunctiontr_2; "CVssFunctionTracer::GetCurrentContexts"
0x180034f9c  mov     [rsp+148h+var_D0], rax
0x180034fa1  lea     rax, aTrctrcc; "TRCTRCC"
0x180034fa8  mov     [rsp+148h+var_C8], rax
0x180034fb0  mov     dword ptr [rsp+148h+var_C0], 37Bh
0x180034fbb  mov     dword ptr [rsp+148h+var_C0+4], 0Bh
0x180034fc6  mov     [rsp+148h+var_B8], 0FFh
0x180034fd1  mov     [rsp+148h+var_38], 1000000h
0x180034fdc  xor     edx, edx; Val
0x180034fde  lea     r8d, [rdx+78h]; Size
0x180034fe2  lea     rcx, [rsp+148h+var_B0]; void *
0x180034fea  call    memset_0
0x180034fef  lea     r9, aInternalTracin; "internal tracing buffer - out of memory"
0x180034ff6  mov     r8d, 8007000Eh
0x180034ffc  lea     rdx, [rsp+148h+var_D8]
0x180035001  mov     rcx, r14
0x180035004  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18003500a  lea     r13, ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180035011  mov     [rsp+148h+var_128], r13; void (*)(void *)
0x180035016  lea     r9, ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; void (*)(void *)
0x18003501d  mov     edx, 20h ; ' '; unsigned __int64
0x180035022  lea     r8d, [rdx-1Ch]; unsigned __int64
0x180035026  lea     rcx, [rsp+148h+var_D8]; void *
0x18003502b  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180035030  nop
0x180035031  xor     ebx, ebx
0x180035033  cmp     ebx, 4
0x180035036  jge     short loc_18003508F
0x180035038  mov     rdi, r14
0x18003503b  test    rdi, rdi
0x18003503e  jz      short loc_18003508B
0x180035040  movsxd  rsi, ebx
0x180035043  mov     rdx, [rdi+rsi*8+40h]
0x180035048  test    rdx, rdx
0x18003504b  jz      short loc_180035085
0x18003504d  lea     rcx, [rsp+148h+var_100]
0x180035052  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180035057  nop
0x180035058  mov     r8, [rax+10h]
0x18003505c  cmp     qword ptr [rax+18h], 7
0x180035061  jbe     short loc_180035066
0x180035063  mov     rax, [rax]
0x180035066  shl     rsi, 5
0x18003506a  lea     rcx, [rsp+148h+var_D8]
0x18003506f  add     rcx, rsi; Src
0x180035072  mov     rdx, rax
0x180035075  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003507a  nop
0x18003507b  lea     rcx, [rsp+148h+var_100]
0x180035080  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035085  mov     rdi, [rdi+60h]
0x180035089  jmp     short loc_18003503B
0x18003508b  inc     ebx
0x18003508d  jmp     short loc_180035033
0x18003508f  xor     ebx, ebx
0x180035091  lea     esi, [rbx+66h]
0x180035094  cmp     ebx, 4
0x180035097  jge     loc_180035143
0x18003509d  movsxd  rdi, ebx
0x1800350a0  shl     rdi, 5
0x1800350a4  cmp     [rsp+rdi+148h+var_C8], 0
0x1800350ad  jbe     loc_18003513C
0x1800350b3  lea     rdx, asc_18005D780; "\n\n"
0x1800350ba  lea     rcx, [rsp+148h+var_118]; this
0x1800350bf  call    ?Append@CVssAutoCoString@@QEAAXPEBG@Z; CVssAutoCoString::Append(ushort const *)
0x1800350c4  mov     ecx, ebx
0x1800350c6  test    ebx, ebx
0x1800350c8  jz      short loc_1800350E9
0x1800350ca  sub     ecx, 1
0x1800350cd  jz      short loc_1800350E1
0x1800350cf  sub     ecx, 1
0x1800350d2  jz      short loc_1800350D9
0x1800350d4  mov     r8d, esi
0x1800350d7  jmp     short loc_1800350EF
0x1800350d9  mov     r8d, 65h ; 'e'
0x1800350df  jmp     short loc_1800350EF
0x1800350e1  mov     r8d, 67h ; 'g'
0x1800350e7  jmp     short loc_1800350EF
0x1800350e9  mov     r8d, 64h ; 'd'
0x1800350ef  lea     rdx, [rsp+148h+var_100]
0x1800350f4  call    ?LoadStringW@CVssResource@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; CVssResource::LoadStringW(uint)
0x1800350f9  nop
0x1800350fa  cmp     qword ptr [rax+18h], 7
0x1800350ff  jbe     short loc_180035104
0x180035101  mov     rax, [rax]
0x180035104  mov     rdx, rax; unsigned __int16 *
0x180035107  lea     rcx, [rsp+148h+var_118]; this
0x18003510c  call    ?Append@CVssAutoCoString@@QEAAXPEBG@Z; CVssAutoCoString::Append(ushort const *)
0x180035111  nop
0x180035112  lea     rcx, [rsp+148h+var_100]
0x180035117  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003511c  lea     rdx, [rsp+148h+var_D8]
0x180035121  add     rdx, rdi
0x180035124  cmp     [rsp+rdi+148h+var_C0], 7
0x18003512d  jbe     short loc_180035132
0x18003512f  mov     rdx, [rdx]; unsigned __int16 *
0x180035132  lea     rcx, [rsp+148h+var_118]; this
0x180035137  call    ?Append@CVssAutoCoString@@QEAAXPEBG@Z; CVssAutoCoString::Append(ushort const *)
0x18003513c  inc     ebx
0x18003513e  jmp     loc_180035094
0x180035143  mov     r9, r13; void (*)(void *)
0x180035146  mov     edx, 20h ; ' '; unsigned __int64
0x18003514b  lea     r8d, [rdx-1Ch]; unsigned __int64
0x18003514f  lea     rcx, [rsp+148h+var_D8]; void *
0x180035154  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180035159  nop
0x18003515a  xor     ecx, ecx; pv
0x18003515c  call    cs:__imp_CoTaskMemFree
0x180035162  mov     rax, [rsp+148h+var_118]
0x180035167  mov     rcx, [rsp+148h+var_28]
0x18003516f  xor     rcx, rsp; StackCookie
0x180035172  call    __security_check_cookie
0x180035177  lea     r11, [rsp+148h+var_18]
0x18003517f  mov     rbx, [r11+28h]
0x180035183  mov     rsi, [r11+30h]
0x180035187  mov     rsp, r11
0x18003518a  pop     r14
0x18003518c  pop     r13
0x18003518e  pop     rdi
0x18003518f  retn
```
