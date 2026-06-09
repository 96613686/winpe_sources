# CMachineLockSettings::_InitDelayLockItems(bool,ulong,ulong,ulong)

- ea: `0x18002c134`
- end: `0x18002c3db`
- name: `?_InitDelayLockItems@CMachineLockSettings@@AEAAJ_NKKK@Z`
- size: `679`
- prototype: `__int64 __fastcall(CMachineLockSettings *this, __int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002b528`

## callees

- `0x180026218`
- `0x18002b2d8`
- `0x18002ba7c`
- `0x18002c004`
- `0x18002c134`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002c2d0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002c2d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c278`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c289`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c2f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c391`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c278`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c289`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c2f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c391`
- `ntdll!WinSqmSetDWORD` at `0x18002c22f`
- `ntdll!WinSqmSetDWORD` at `0x18002c24e`
- `ntdll!WinSqmSetDWORD` at `0x18002c22f`
- `ntdll!WinSqmSetDWORD` at `0x18002c24e`

## pseudocode

```c
__int64 __fastcall CMachineLockSettings::_InitDelayLockItems(
        CMachineLockSettings *this,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5)
{
  unsigned int v7; // r13d
  int v8; // eax
  int v9; // eax
  __int64 v10; // r8
  unsigned int CurrentDelayLockSettings; // eax
  unsigned int v12; // r12d
  LPVOID *v13; // r14
  int v14; // esi
  unsigned __int64 *v15; // rdi
  unsigned __int64 i; // r15
  __int64 v17; // rdi
  __int64 v18; // r8
  bool v19; // al
  const wchar_t *v20; // r9
  unsigned __int64 v22; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+28h] [rbp-D8h] BYREF
  int v24; // [rsp+30h] [rbp-D0h]
  bool v25; // [rsp+34h] [rbp-CCh]
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF

  v22 = __PAIR64__(a3, a4);
  *((_DWORD *)this + 12) = 0;
  if ( (*((_BYTE *)this + 52) & 1) != 0 )
  {
    v7 = 0;
    v22 = 0;
    *((_DWORD *)this + 12) = 1;
  }
  else
  {
    v8 = 0;
    if ( a3 != -1 )
    {
      *((_DWORD *)this + 12) = 1;
      v8 = 1;
    }
    if ( a4 != -1 )
    {
      v8 |= 2u;
      *((_DWORD *)this + 12) = v8;
    }
    v7 = a5;
    if ( a5 != -1 )
      *((_DWORD *)this + 12) = v8 | 4;
    LogComment(0, L"GP timeout: 0x%x");
    LogComment(0, L"EAS timeout: 0x%x", a5);
    LogComment(0, L"Power settings timeout: 0x%x", a4);
    v9 = *((_DWORD *)this + 12);
    if ( v9 )
    {
      if ( (v9 & 1) != 0 )
        v10 = 1;
      else
        v10 = (~(_BYTE)v9 & 4 | 8u) >> 2;
    }
    else
    {
      v10 = 0;
    }
    WinSqmSetDWORD(0, 10765, v10);
  }
  CurrentDelayLockSettings = CMachineLockSettings::_GetCurrentDelayLockSettings(this);
  v12 = CurrentDelayLockSettings;
  if ( CurrentDelayLockSettings != -252645136 )
    WinSqmSetDWORD(0, 10767, CurrentDelayLockSettings);
  v13 = (LPVOID *)((char *)this + 8);
  v14 = 0;
  v15 = (unsigned __int64 *)((char *)this + 16);
  if ( *((_QWORD *)this + 1) )
  {
    for ( i = 0; i < *v15; ++i )
      CoTaskMemFree(*((LPVOID *)*v13 + 2 * i));
    CoTaskMemFree(*v13);
    *v13 = 0;
  }
  *v15 = 0;
  v17 = 0;
  *((_QWORD *)this + 4) = 0;
  while ( (unsigned int)v17 < 8 && *((_DWORD *)qword_18008A060 + v17) <= (unsigned int)v22 )
  {
    if ( (unsigned int)(LoadStringW(g_hinst, v17 + 2210, Buffer, 260) - 1) > 0x103 )
      return (unsigned int)-2147024774;
    pv = 0;
    v24 = 0;
    v25 = 0;
    CoTaskMemFree(0);
    v14 = CoAllocString(Buffer, (unsigned __int16 **)&pv);
    if ( v14 >= 0 )
    {
      v18 = *((unsigned int *)qword_18008A060 + v17);
      v24 = v18;
      v19 = (unsigned int)v18 <= HIDWORD(v22) && (unsigned int)v18 <= v7;
      v25 = v19;
      v20 = L"ENABLED";
      if ( !v19 )
        v20 = L"DISABLED";
      LogComment(0, L"Adding: %d secs, %s", v18, v20, v22);
      v14 = CTSimpleArray<CMachineLockSettings::DELAY_LOCK_ITEM,4294967294,CTPolicyCoTaskMem<CMachineLockSettings::DELAY_LOCK_ITEM>,CSimpleArrayStandardCompareHelper<CMachineLockSettings::DELAY_LOCK_ITEM>,CSimpleArrayStandardMergeHelper<CMachineLockSettings::DELAY_LOCK_ITEM>>::Add(
              (char *)this + 8,
              &pv);
      if ( v14 >= 0 && v25 )
      {
        if ( *((_DWORD *)qword_18008A060 + v17) <= v12 )
        {
          *((_DWORD *)this + 10) = v17;
          *((_DWORD *)this + 11) = v17;
        }
        if ( (_DWORD)v17 )
          *((_DWORD *)this + 12) &= ~2u;
      }
    }
    CoTaskMemFree(pv);
    v17 = (unsigned int)(v17 + 1);
    if ( v14 < 0 )
      return (unsigned int)v14;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18002c134  mov     [rsp-8+arg_8], rbx
0x18002c139  push    rbp
0x18002c13a  push    rsi
0x18002c13b  push    rdi
0x18002c13c  push    r12
0x18002c13e  push    r13
0x18002c140  push    r14
0x18002c142  push    r15
0x18002c144  lea     rbp, [rsp-160h]
0x18002c14c  sub     rsp, 260h
0x18002c153  mov     rax, cs:__security_cookie
0x18002c15a  xor     rax, rsp
0x18002c15d  mov     [rbp+190h+var_40], rax
0x18002c164  mov     r14d, 1
0x18002c16a  mov     [rsp+290h+var_270], r9d
0x18002c16f  mov     esi, r9d
0x18002c172  mov     [rsp+290h+var_26C], r8d
0x18002c177  mov     rbx, rcx
0x18002c17a  mov     dword ptr [rcx+30h], 0
0x18002c181  test    [rcx+34h], r14b
0x18002c185  jz      short loc_18002C1A3
0x18002c187  mov     [rsp+290h+var_26C], 0
0x18002c18f  xor     r13d, r13d
0x18002c192  mov     [rsp+290h+var_270], 0
0x18002c19a  mov     [rcx+30h], r14d
0x18002c19e  jmp     loc_18002C235
0x18002c1a3  xor     eax, eax
0x18002c1a5  or      ecx, 0FFFFFFFFh
0x18002c1a8  cmp     r8d, ecx
0x18002c1ab  jnb     short loc_18002C1B4
0x18002c1ad  mov     [rbx+30h], r14d
0x18002c1b1  mov     eax, r14d
0x18002c1b4  cmp     esi, ecx
0x18002c1b6  jnb     short loc_18002C1BE
0x18002c1b8  or      eax, 2
0x18002c1bb  mov     [rbx+30h], eax
0x18002c1be  mov     r13d, [rbp+190h+arg_20]
0x18002c1c5  cmp     r13d, ecx
0x18002c1c8  jnb     short loc_18002C1D0
0x18002c1ca  or      eax, 4
0x18002c1cd  mov     [rbx+30h], eax
0x18002c1d0  lea     rdx, aGpTimeout0xX; "GP timeout: 0x%x"
0x18002c1d7  xor     ecx, ecx; bool
0x18002c1d9  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002c1de  mov     r8d, r13d
0x18002c1e1  lea     rdx, aEasTimeout0xX; "EAS timeout: 0x%x"
0x18002c1e8  xor     ecx, ecx; bool
0x18002c1ea  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002c1ef  mov     r8d, esi
0x18002c1f2  lea     rdx, aPowerSettingsT; "Power settings timeout: 0x%x"
0x18002c1f9  xor     ecx, ecx; bool
0x18002c1fb  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002c200  mov     eax, [rbx+30h]
0x18002c203  test    eax, eax
0x18002c205  jnz     short loc_18002C20C
0x18002c207  xor     r8d, r8d
0x18002c20a  jmp     short loc_18002C228
0x18002c20c  test    r14b, al
0x18002c20f  jz      short loc_18002C216
0x18002c211  mov     r8d, r14d
0x18002c214  jmp     short loc_18002C228
0x18002c216  not     al
0x18002c218  movzx   r8d, al
0x18002c21c  and     r8d, 4
0x18002c220  or      r8d, 8
0x18002c224  shr     r8d, 2
0x18002c228  mov     edx, 2A0Dh
0x18002c22d  xor     ecx, ecx
0x18002c22f  call    cs:__imp_WinSqmSetDWORD
0x18002c235  call    ?_GetCurrentDelayLockSettings@CMachineLockSettings@@AEAAKXZ; CMachineLockSettings::_GetCurrentDelayLockSettings(void)
0x18002c23a  mov     r12d, eax
0x18002c23d  cmp     eax, 0F0F0F0F0h
0x18002c242  jz      short loc_18002C254
0x18002c244  mov     r8d, eax
0x18002c247  mov     edx, 2A0Fh
0x18002c24c  xor     ecx, ecx
0x18002c24e  call    cs:__imp_WinSqmSetDWORD
0x18002c254  lea     r14, [rbx+8]
0x18002c258  xor     esi, esi
0x18002c25a  lea     rdi, [r14+8]
0x18002c25e  cmp     [r14], rsi
0x18002c261  jz      short loc_18002C292
0x18002c263  xor     r15d, r15d
0x18002c266  cmp     [rdi], rsi
0x18002c269  jbe     short loc_18002C286
0x18002c26b  mov     rcx, [r14]
0x18002c26e  mov     rax, r15
0x18002c271  add     rax, rax
0x18002c274  mov     rcx, [rcx+rax*8]; pv
0x18002c278  call    cs:__imp_CoTaskMemFree
0x18002c27e  inc     r15
0x18002c281  cmp     r15, [rdi]
0x18002c284  jb      short loc_18002C26B
0x18002c286  mov     rcx, [r14]; pv
0x18002c289  call    cs:__imp_CoTaskMemFree
0x18002c28f  mov     [r14], rsi
0x18002c292  mov     [rdi], rsi
0x18002c295  lea     rcx, qword_18008A060
0x18002c29c  xor     edi, edi
0x18002c29e  mov     [r14+18h], rsi
0x18002c2a2  cmp     edi, 8
0x18002c2a5  jnb     loc_18002C3AF
0x18002c2ab  mov     eax, [rsp+290h+var_270]
0x18002c2af  cmp     [rcx+rdi*4], eax
0x18002c2b2  ja      loc_18002C3AF
0x18002c2b8  mov     rcx, cs:g_hinst; hInstance
0x18002c2bf  lea     edx, [rdi+8A2h]; uID
0x18002c2c5  mov     r9d, 104h; cchBufferMax
0x18002c2cb  lea     r8, [rsp+290h+Buffer]; lpBuffer
0x18002c2d0  call    cs:__imp_LoadStringW
0x18002c2d6  dec     eax
0x18002c2d8  cmp     eax, 103h
0x18002c2dd  ja      loc_18002C3AA
0x18002c2e3  xor     eax, eax
0x18002c2e5  xor     ecx, ecx; pv
0x18002c2e7  mov     [rsp+290h+pv], rax
0x18002c2ec  mov     [rsp+290h+var_260], eax
0x18002c2f0  mov     [rsp+290h+var_25C], al
0x18002c2f4  call    cs:__imp_CoTaskMemFree
0x18002c2fa  lea     rdx, [rsp+290h+pv]; unsigned __int16 **
0x18002c2ff  lea     rcx, [rsp+290h+Buffer]; unsigned __int16 *
0x18002c304  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18002c309  mov     esi, eax
0x18002c30b  test    eax, eax
0x18002c30d  js      short loc_18002C38C
0x18002c30f  lea     r8, qword_18008A060
0x18002c316  mov     r8d, [r8+rdi*4]
0x18002c31a  mov     [rsp+290h+var_260], r8d
0x18002c31f  cmp     r8d, [rsp+290h+var_26C]
0x18002c324  ja      short loc_18002C32F
0x18002c326  cmp     r8d, r13d
0x18002c329  ja      short loc_18002C32F
0x18002c32b  mov     al, 1
0x18002c32d  jmp     short loc_18002C331
0x18002c32f  xor     al, al
0x18002c331  lea     rcx, aDisabled; "DISABLED"
0x18002c338  mov     [rsp+290h+var_25C], al
0x18002c33c  test    al, al
0x18002c33e  lea     r9, aEnabled_0; "ENABLED"
0x18002c345  lea     rdx, aAddingDSecsS; "Adding: %d secs, %s"
0x18002c34c  cmovz   r9, rcx
0x18002c350  xor     ecx, ecx; bool
0x18002c352  call    ?LogComment@@YAX_NPEBGZZ; LogComment(bool,ushort const *,...)
0x18002c357  lea     rdx, [rsp+290h+pv]
0x18002c35c  mov     rcx, r14
0x18002c35f  call    ?Add@?$CTSimpleArray@UDELAY_LOCK_ITEM@CMachineLockSettings@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UDELAY_LOCK_ITEM@CMachineLockSettings@@@@V?$CSimpleArrayStandardCompareHelper@UDELAY_LOCK_ITEM@CMachineLockSettings@@@@V?$CSimpleArrayStandardMergeHelper@UDELAY_LOCK_ITEM@CMachineLockSettings@@@@@@QEAAJAEBUDELAY_LOCK_ITEM@CMachineLockSettings@@PEA_K@Z; CTSimpleArray<CMachineLockSettings::DELAY_LOCK_ITEM,4294967294,CTPolicyCoTaskMem<CMachineLockSettings::DELAY_LOCK_ITEM>,CSimpleArrayStandardCompareHelper<CMachineLockSettings::DELAY_LOCK_ITEM>,CSimpleArrayStandardMergeHelper<CMachineLockSettings::DELAY_LOCK_ITEM>>::Add(CMachineLockSettings::DELAY_LOCK_ITEM const &,unsigned __int64 *)
0x18002c364  mov     esi, eax
0x18002c366  test    eax, eax
0x18002c368  js      short loc_18002C38C
0x18002c36a  cmp     [rsp+290h+var_25C], 0
0x18002c36f  jz      short loc_18002C38C
0x18002c371  lea     rax, qword_18008A060
0x18002c378  cmp     [rax+rdi*4], r12d
0x18002c37c  ja      short loc_18002C384
0x18002c37e  mov     [rbx+28h], edi
0x18002c381  mov     [rbx+2Ch], edi
0x18002c384  test    edi, edi
0x18002c386  jz      short loc_18002C38C
0x18002c388  and     dword ptr [rbx+30h], 0FFFFFFFDh
0x18002c38c  mov     rcx, [rsp+290h+pv]; pv
0x18002c391  call    cs:__imp_CoTaskMemFree
0x18002c397  inc     edi
0x18002c399  lea     rcx, qword_18008A060
0x18002c3a0  test    esi, esi
0x18002c3a2  jns     loc_18002C2A2
0x18002c3a8  jmp     short loc_18002C3AF
0x18002c3aa  mov     esi, 8007007Ah
0x18002c3af  mov     eax, esi
0x18002c3b1  mov     rcx, [rbp+190h+var_40]
0x18002c3b8  xor     rcx, rsp; StackCookie
0x18002c3bb  call    __security_check_cookie
0x18002c3c0  mov     rbx, [rsp+290h+arg_8]
0x18002c3c8  add     rsp, 260h
0x18002c3cf  pop     r15
0x18002c3d1  pop     r14
0x18002c3d3  pop     r13
0x18002c3d5  pop     r12
0x18002c3d7  pop     rdi
0x18002c3d8  pop     rsi
0x18002c3d9  pop     rbp
0x18002c3da  retn
```
