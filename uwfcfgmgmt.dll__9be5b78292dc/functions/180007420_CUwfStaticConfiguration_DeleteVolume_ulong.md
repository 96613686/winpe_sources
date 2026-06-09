# CUwfStaticConfiguration::DeleteVolume(ulong)

- ea: `0x180007420`
- end: `0x1800075ec`
- name: `?DeleteVolume@CUwfStaticConfiguration@@QEAAJK@Z`
- size: `460`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x1800197d0`

## callees

- `0x1800054d0`
- `0x180006ae0`
- `0x180007390`
- `0x180007420`
- `0x1800079a0`
- `0x180008cf0`
- `0x18000c0f0`
- `0x18000d5f0`
- `0x18000de30`
- `0x18000e0f0`
- `0x18001b020`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::DeleteVolume(CUwfStaticConfiguration *this, unsigned int a2)
{
  CUwfConfiguration *v3; // rcx
  int v5; // ebx
  unsigned int v6; // esi
  bool v7; // zf
  HKEY v8; // rdx
  unsigned int v10; // [rsp+30h] [rbp-50h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int16 v12[8]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v13; // [rsp+50h] [rbp-30h]
  WCHAR SubKey[8]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v15; // [rsp+68h] [rbp-18h]

  v10 = 0;
  v15 = 0;
  v3 = (CUwfConfiguration *)*((_QWORD *)this + 4);
  v13 = 0;
  *(_OWORD *)SubKey = 0;
  *(_OWORD *)v12 = 0;
  v5 = CUwfConfiguration::FixupUpdatedSettings(v3);
  if ( v5 < 0 )
    goto LABEL_14;
  CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(this);
  v5 = CUwfRegKey::QueryDWORDValue((CUwfStaticConfiguration *)((char *)this + 24), L"NumVolumes", &v10);
  if ( v5 < 0 )
    goto LABEL_14;
  v6 = a2 + 1;
  v7 = a2 + 1 == v10;
  if ( a2 + 1 < v10 )
  {
    while ( 1 )
    {
      v5 = StringCchPrintfW(SubKey, 0xCu, L"%i", v6 - 1);
      if ( v5 < 0 )
        goto LABEL_14;
      v5 = StringCchPrintfW(v12, 0xCu, L"%i", v6);
      if ( v5 < 0 )
        goto LABEL_14;
      v8 = (HKEY)*((_QWORD *)this + 3);
      phkResult = 0;
      v5 = CUwfRegKey::Open(&phkResult, v8, SubKey, 0xF003Fu);
      if ( v5 < 0
        || (v5 = CUwfConfiguration::CopyTree(
                   *((CUwfConfiguration **)this + 4),
                   (CUwfStaticConfiguration *)((char *)this + 24),
                   v12,
                   phkResult,
                   1),
            v5 < 0) )
      {
        CUwfRegKey::Close(&phkResult);
        goto LABEL_14;
      }
      CUwfRegKey::Close(&phkResult);
      if ( ++v6 >= v10 )
      {
        v7 = a2 + 1 == v10;
        break;
      }
    }
  }
  if ( v7 && (v5 = StringCchPrintfW(v12, 0xCu, L"%i", a2), v5 < 0)
    || (v5 = CUwfConfiguration::DeleteTreeFromRoot(*((CUwfConfiguration **)this + 4), (HKEY *)this + 3, v12), v5 < 0)
    || (v5 = CUwfStaticConfiguration::set_NumVolumes(this, v10 - 1), v5 < 0) )
  {
LABEL_14:
    *(_DWORD *)(*((_QWORD *)this + 4) + 16LL) = v5;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180007420  mov     [rsp-28h+arg_10], rbx
0x180007425  mov     [rsp-28h+arg_18], rsi
0x18000742a  push    rbp
0x18000742b  push    rdi
0x18000742c  push    r13
0x18000742e  push    r14
0x180007430  push    r15
0x180007432  mov     rbp, rsp
0x180007435  sub     rsp, 80h
0x18000743c  mov     rax, cs:__security_cookie
0x180007443  xor     rax, rsp
0x180007446  mov     [rbp+var_10], rax
0x18000744a  xor     eax, eax
0x18000744c  mov     [rbp+var_50], 0
0x180007453  mov     rdi, rcx
0x180007456  mov     [rbp+var_18], rax
0x18000745a  mov     rcx, [rcx+20h]; this
0x18000745e  xorps   xmm0, xmm0
0x180007461  xorps   xmm1, xmm1
0x180007464  mov     [rbp+var_30], rax
0x180007468  movups  xmmword ptr [rbp+SubKey], xmm0
0x18000746c  mov     r13d, edx
0x18000746f  movups  xmmword ptr [rbp+var_40], xmm1
0x180007473  call    ?FixupUpdatedSettings@CUwfConfiguration@@QEAAJXZ; CUwfConfiguration::FixupUpdatedSettings(void)
0x180007478  mov     ebx, eax
0x18000747a  test    eax, eax
0x18000747c  js      loc_1800075B0
0x180007482  mov     rcx, rdi; this
0x180007485  call    ?ReleaseStaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(void)
0x18000748a  lea     r14, [rdi+18h]
0x18000748e  mov     rcx, r14; this
0x180007491  lea     r8, [rbp+var_50]; unsigned int *
0x180007495  lea     rdx, aNumvolumes; "NumVolumes"
0x18000749c  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x1800074a1  mov     ebx, eax
0x1800074a3  test    eax, eax
0x1800074a5  js      loc_1800075B0
0x1800074ab  mov     eax, [rbp+var_50]
0x1800074ae  lea     r15d, [r13+1]
0x1800074b2  mov     esi, r15d
0x1800074b5  cmp     r15d, eax
0x1800074b8  jnb     loc_180007567
0x1800074be  lea     r9d, [rsi-1]
0x1800074c2  mov     edx, 0Ch; unsigned __int64
0x1800074c7  lea     r8, aI; "%i"
0x1800074ce  lea     rcx, [rbp+SubKey]; unsigned __int16 *
0x1800074d2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800074d7  mov     ebx, eax
0x1800074d9  test    eax, eax
0x1800074db  js      loc_1800075B0
0x1800074e1  mov     r9d, esi
0x1800074e4  lea     r8, aI; "%i"
0x1800074eb  mov     edx, 0Ch; unsigned __int64
0x1800074f0  lea     rcx, [rbp+var_40]; unsigned __int16 *
0x1800074f4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800074f9  mov     ebx, eax
0x1800074fb  test    eax, eax
0x1800074fd  js      loc_1800075B0
0x180007503  mov     rdx, [r14]; hKey
0x180007506  lea     r8, [rbp+SubKey]; lpSubKey
0x18000750a  mov     r9d, 0F003Fh; samDesired
0x180007510  mov     [rbp+phkResult], 0
0x180007518  lea     rcx, [rbp+phkResult]; phkResult
0x18000751c  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180007521  mov     ebx, eax
0x180007523  test    eax, eax
0x180007525  js      loc_1800075E1
0x18000752b  mov     r9, [rbp+phkResult]; HKEY
0x18000752f  lea     r8, [rbp+var_40]; unsigned __int16 *
0x180007533  mov     rcx, [rdi+20h]; this
0x180007537  mov     rdx, r14; struct CUwfRegKey *
0x18000753a  mov     [rsp+80h+var_60], 1; bool
0x18000753f  call    ?CopyTree@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGPEAUHKEY__@@_N@Z; CUwfConfiguration::CopyTree(CUwfRegKey &,ushort const *,HKEY__ *,bool)
0x180007544  lea     rcx, [rbp+phkResult]; this
0x180007548  mov     ebx, eax
0x18000754a  test    eax, eax
0x18000754c  js      loc_1800075E5
0x180007552  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x180007557  mov     eax, [rbp+var_50]
0x18000755a  inc     esi
0x18000755c  cmp     esi, eax
0x18000755e  jb      loc_1800074BE
0x180007564  cmp     r15d, eax
0x180007567  jnz     short loc_180007587
0x180007569  mov     r9d, r13d
0x18000756c  lea     r8, aI; "%i"
0x180007573  mov     edx, 0Ch; unsigned __int64
0x180007578  lea     rcx, [rbp+var_40]; unsigned __int16 *
0x18000757c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007581  mov     ebx, eax
0x180007583  test    eax, eax
0x180007585  js      short loc_1800075B0
0x180007587  mov     rcx, [rdi+20h]; this
0x18000758b  lea     r8, [rbp+var_40]; unsigned __int16 *
0x18000758f  mov     rdx, r14; struct CUwfRegKey *
0x180007592  call    ?DeleteTreeFromRoot@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBG@Z; CUwfConfiguration::DeleteTreeFromRoot(CUwfRegKey &,ushort const *)
0x180007597  mov     ebx, eax
0x180007599  test    eax, eax
0x18000759b  js      short loc_1800075B0
0x18000759d  mov     edx, [rbp+var_50]
0x1800075a0  mov     rcx, rdi; this
0x1800075a3  dec     edx; unsigned int
0x1800075a5  call    ?set_NumVolumes@CUwfStaticConfiguration@@QEAAJK@Z; CUwfStaticConfiguration::set_NumVolumes(ulong)
0x1800075aa  mov     ebx, eax
0x1800075ac  test    eax, eax
0x1800075ae  jns     short loc_1800075B7
0x1800075b0  mov     rax, [rdi+20h]
0x1800075b4  mov     [rax+10h], ebx
0x1800075b7  mov     eax, ebx
0x1800075b9  mov     rcx, [rbp+var_10]
0x1800075bd  xor     rcx, rsp; StackCookie
0x1800075c0  call    __security_check_cookie
0x1800075c5  lea     r11, [rsp+80h+var_s0]
0x1800075cd  mov     rbx, [r11+40h]
0x1800075d1  mov     rsi, [r11+48h]
0x1800075d5  mov     rsp, r11
0x1800075d8  pop     r15
0x1800075da  pop     r14
0x1800075dc  pop     r13
0x1800075de  pop     rdi
0x1800075df  pop     rbp
0x1800075e0  retn
0x1800075e1  lea     rcx, [rbp+phkResult]; this
0x1800075e5  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x1800075ea  jmp     short loc_1800075B0
```
