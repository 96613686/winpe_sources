# CSilentProcessExitSettings::Load(ushort const *,void *)

- ea: `0x1800148a8`
- end: `0x180014b23`
- name: `?Load@CSilentProcessExitSettings@@QEAAJPEBGPEAX@Z`
- size: `635`
- prototype: `__int64 __fastcall(CSilentProcessExitSettings *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010234`

## callees

- `0x1800035dc`
- `0x180003604`
- `0x180005c20`
- `0x180005c80`
- `0x180009580`
- `0x1800098f8`
- `0x180009a78`
- `0x180009c80`
- `0x18000ad10`
- `0x180014860`
- `0x1800148a8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180014a09`
- `ADVAPI32!RegOpenKeyExW` at `0x180014a56`
- `ADVAPI32!RegOpenKeyExW` at `0x180014a09`
- `ADVAPI32!RegOpenKeyExW` at `0x180014a56`
- `KERNEL32!IsWow64Process` at `0x1800149cb`
- `KERNEL32!IsWow64Process` at `0x1800149cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSilentProcessExitSettings::Load(
        CSilentProcessExitSettings *this,
        const unsigned __int16 *a2,
        void *a3)
{
  unsigned int v6; // r14d
  REGSAM v7; // edi
  signed int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  HKEY *v12; // rax
  LSTATUS v13; // eax
  unsigned int v14; // r8d
  unsigned int *v15; // r9
  HKEY *v16; // rax
  unsigned int v17; // r8d
  unsigned int *v18; // r9
  unsigned int phkResult; // [rsp+20h] [rbp-30h]
  unsigned int phkResulta; // [rsp+20h] [rbp-30h]
  LPCWSTR lpSubKey[4]; // [rsp+30h] [rbp-20h] BYREF
  WINBOOL Wow64Process; // [rsp+88h] [rbp+38h] BYREF
  HKEY v24; // [rsp+98h] [rbp+48h] BYREF

  v24 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpSubKey);
  if ( a2 && a3 )
  {
    v6 = 0;
    v7 = 1;
    while ( v6 < 7 )
    {
      v8 = CRegSetting::Initialize(
             (char *)this + 104 * LODWORD(qword_180019510[4 * v6 + 2]),
             LODWORD(qword_180019510[4 * v6]),
             &lParam,
             qword_180019510[4 * v6 + 1],
             qword_180019510[4 * v6 + 3]);
      if ( v8 < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 11;
LABEL_10:
          WPP_SF_d(v9[2], v10, WPP_f0cc02b161843d0fe17f666dff29f118_Traceguids, (unsigned int)v8);
          goto LABEL_27;
        }
        goto LABEL_27;
      }
      ++v6;
    }
    v8 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
           lpSubKey,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\SilentProcessExit\\%ls",
           a2);
    if ( v8 >= 0 )
    {
      Wow64Process = 0;
      v11 = IsWow64Process(a3, &Wow64Process);
      if ( v11 )
        v11 = Wow64Process;
      else
        Wow64Process = 0;
      if ( v11 )
        v7 = 513;
      v12 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v24);
      v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, v7, v12);
      v8 = v13;
      if ( v13
        || (CRegSetting::Load(v24, this, v14, v15, phkResult),
            v16 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v24),
            v13 = RegOpenKeyExW(
                    HKEY_LOCAL_MACHINE,
                    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\SilentProcessExit",
                    0,
                    0x101u,
                    v16),
            (v8 = v13) != 0) )
      {
        if ( v13 != 2 )
        {
          if ( v13 > 0 )
            v8 = (unsigned __int16)v13 | 0x80070000;
          goto LABEL_27;
        }
      }
      else
      {
        CRegSetting::Load(v24, this, v17, v18, phkResulta);
      }
      v8 = 0;
      goto LABEL_27;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 12;
      goto LABEL_10;
    }
LABEL_27:
    if ( *(_QWORD *)((char *)this + (-(__int64)(*((_BYTE *)this + 208) != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 304) )
      UtilExpandEnvironmentStrings(*(LPCWSTR *)((char *)this
                                              + (-(__int64)(*((_BYTE *)this + 208) != 0) & 0xFFFFFFFFFFFFFFA8uLL)
                                              + 304));
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpSubKey);
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v24);
    return (unsigned int)v8;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_f0cc02b161843d0fe17f666dff29f118_Traceguids);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpSubKey);
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v24);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800148a8  mov     [rsp-28h+arg_0], rbx
0x1800148ad  mov     [rsp-28h+arg_10], rsi
0x1800148b2  push    rbp
0x1800148b3  push    rdi
0x1800148b4  push    r12
0x1800148b6  push    r14
0x1800148b8  push    r15
0x1800148ba  mov     rbp, rsp
0x1800148bd  sub     rsp, 50h
0x1800148c1  mov     rsi, rcx
0x1800148c4  mov     [rbp+arg_18], 0
0x1800148cc  lea     rcx, [rbp+lpSubKey]; void *
0x1800148d0  mov     r15, r8
0x1800148d3  mov     r12, rdx
0x1800148d6  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x1800148db  test    r12, r12
0x1800148de  jz      loc_180014AC2
0x1800148e4  test    r15, r15
0x1800148e7  jz      loc_180014AC2
0x1800148ed  xor     r14d, r14d
0x1800148f0  lea     edi, [r14+1]
0x1800148f4  lea     r10, qword_180019510
0x1800148fb  cmp     r14d, 7
0x1800148ff  jnb     short loc_18001497C
0x180014901  mov     edx, r14d
0x180014904  lea     r8, lParam
0x18001490b  shl     rdx, 5
0x18001490f  mov     eax, [rdx+r10+10h]
0x180014914  mov     r9, [rdx+r10+8]
0x180014919  imul    rcx, rax, 68h ; 'h'
0x18001491d  mov     rax, [rdx+r10+18h]
0x180014922  mov     edx, [rdx+r10]
0x180014926  add     rcx, rsi
0x180014929  mov     qword ptr [rsp+50h+phkResult], rax
0x18001492e  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEBG1_K@Z; CRegSetting::Initialize(_DataType,ushort const *,ushort const *,unsigned __int64)
0x180014933  mov     ebx, eax
0x180014935  test    eax, eax
0x180014937  js      short loc_18001493E
0x180014939  add     r14d, edi
0x18001493c  jmp     short loc_1800148F4
0x18001493e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014945  lea     rax, WPP_GLOBAL_Control
0x18001494c  cmp     rcx, rax
0x18001494f  jz      loc_180014A70
0x180014955  test    [rcx+1Ch], dil
0x180014959  jz      loc_180014A70
0x18001495f  mov     edx, 0Bh
0x180014964  mov     rcx, [rcx+10h]
0x180014968  lea     r8, WPP_f0cc02b161843d0fe17f666dff29f118_Traceguids
0x18001496f  mov     r9d, ebx
0x180014972  call    WPP_SF_d
0x180014977  jmp     loc_180014A70
0x18001497c  mov     r8, r12
0x18001497f  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180014986  lea     rcx, [rbp+lpSubKey]
0x18001498a  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x18001498f  mov     ebx, eax
0x180014991  test    eax, eax
0x180014993  jns     short loc_1800149BD
0x180014995  mov     rcx, cs:WPP_GLOBAL_Control
0x18001499c  lea     rax, WPP_GLOBAL_Control
0x1800149a3  cmp     rcx, rax
0x1800149a6  jz      loc_180014A70
0x1800149ac  test    [rcx+1Ch], dil
0x1800149b0  jz      loc_180014A70
0x1800149b6  mov     edx, 0Ch
0x1800149bb  jmp     short loc_180014964
0x1800149bd  lea     rdx, [rbp+Wow64Process]; Wow64Process
0x1800149c1  mov     [rbp+Wow64Process], 0
0x1800149c8  mov     rcx, r15; hProcess
0x1800149cb  call    cs:__imp_IsWow64Process
0x1800149d1  test    eax, eax
0x1800149d3  jnz     short loc_1800149DA
0x1800149d5  mov     [rbp+Wow64Process], eax
0x1800149d8  jmp     short loc_1800149DD
0x1800149da  mov     eax, [rbp+Wow64Process]
0x1800149dd  test    eax, eax
0x1800149df  mov     ecx, 201h
0x1800149e4  cmovnz  edi, ecx
0x1800149e7  lea     rcx, [rbp+arg_18]
0x1800149eb  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800149f0  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800149f4  mov     r9d, edi; samDesired
0x1800149f7  mov     rdi, 0FFFFFFFF80000002h
0x1800149fe  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int
0x180014a03  mov     rcx, rdi; hKey
0x180014a06  xor     r8d, r8d; ulOptions
0x180014a09  call    cs:__imp_RegOpenKeyExW
0x180014a0f  mov     ebx, eax
0x180014a11  test    eax, eax
0x180014a13  jz      short loc_180014A29
0x180014a15  cmp     eax, 2
0x180014a18  jz      short loc_180014A6E
0x180014a1a  test    eax, eax
0x180014a1c  jle     short loc_180014A70
0x180014a1e  movzx   ebx, ax
0x180014a21  or      ebx, 80070000h
0x180014a27  jmp     short loc_180014A70
0x180014a29  mov     rcx, [rbp+arg_18]; HKEY
0x180014a2d  mov     rdx, rsi; struct CRegSetting *
0x180014a30  call    ?Load@CRegSetting@@SAJPEAUHKEY__@@QEAV1@KPEAKK@Z; CRegSetting::Load(HKEY__ *,CRegSetting * const,ulong,ulong *,ulong)
0x180014a35  lea     rcx, [rbp+arg_18]
0x180014a39  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180014a3e  mov     r9d, 101h; samDesired
0x180014a44  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int
0x180014a49  xor     r8d, r8d; ulOptions
0x180014a4c  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180014a53  mov     rcx, rdi; hKey
0x180014a56  call    cs:__imp_RegOpenKeyExW
0x180014a5c  mov     ebx, eax
0x180014a5e  test    eax, eax
0x180014a60  jnz     short loc_180014A15
0x180014a62  mov     rcx, [rbp+arg_18]; HKEY
0x180014a66  mov     rdx, rsi; struct CRegSetting *
0x180014a69  call    ?Load@CRegSetting@@SAJPEAUHKEY__@@QEAV1@KPEAKK@Z; CRegSetting::Load(HKEY__ *,CRegSetting * const,ulong,ulong *,ulong)
0x180014a6e  xor     ebx, ebx
0x180014a70  mov     r8b, [rsi+0D0h]
0x180014a77  mov     al, r8b
0x180014a7a  neg     al
0x180014a7c  sbb     rcx, rcx
0x180014a7f  and     rcx, 0FFFFFFFFFFFFFFA8h
0x180014a83  cmp     qword ptr [rcx+rsi+130h], 0
0x180014a8c  jz      short loc_180014AAC
0x180014a8e  neg     r8b
0x180014a91  lea     rdx, [rsi+2D8h]
0x180014a98  sbb     rcx, rcx
0x180014a9b  and     rcx, 0FFFFFFFFFFFFFFA8h
0x180014a9f  mov     rcx, [rcx+rsi+130h]; lpSrc
0x180014aa7  call    ?UtilExpandEnvironmentStrings@@YAJPEBGPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; UtilExpandEnvironmentStrings(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180014aac  lea     rcx, [rbp+lpSubKey]
0x180014ab0  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180014ab5  lea     rcx, [rbp+arg_18]
0x180014ab9  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180014abe  mov     eax, ebx
0x180014ac0  jmp     short loc_180014B0A
0x180014ac2  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ac9  lea     rax, WPP_GLOBAL_Control
0x180014ad0  cmp     rcx, rax
0x180014ad3  jz      short loc_180014AF3
0x180014ad5  mov     edi, 1
0x180014ada  test    [rcx+1Ch], dil
0x180014ade  jz      short loc_180014AF3
0x180014ae0  mov     rcx, [rcx+10h]
0x180014ae4  lea     edx, [rdi+9]
0x180014ae7  lea     r8, WPP_f0cc02b161843d0fe17f666dff29f118_Traceguids
0x180014aee  call    WPP_SF_
0x180014af3  lea     rcx, [rbp+lpSubKey]
0x180014af7  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180014afc  lea     rcx, [rbp+arg_18]
0x180014b00  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180014b05  mov     eax, 80070057h
0x180014b0a  lea     r11, [rsp+50h+var_s0]
0x180014b0f  mov     rbx, [r11+30h]
0x180014b13  mov     rsi, [r11+40h]
0x180014b17  mov     rsp, r11
0x180014b1a  pop     r15
0x180014b1c  pop     r14
0x180014b1e  pop     r12
0x180014b20  pop     rdi
0x180014b21  pop     rbp
0x180014b22  retn
```
