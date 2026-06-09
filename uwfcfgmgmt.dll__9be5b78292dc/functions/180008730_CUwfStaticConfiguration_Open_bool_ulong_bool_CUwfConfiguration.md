# CUwfStaticConfiguration::Open(bool,ulong,bool,CUwfConfiguration *)

- ea: `0x180008730`
- end: `0x1800088f0`
- name: `?Open@CUwfStaticConfiguration@@QEAAJ_NK0PEAVCUwfConfiguration@@@Z`
- size: `448`
- prototype: `__int64 __fastcall(HKEY *this, char, int, char, struct CUwfConfiguration *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180008170`

## callees

- `0x180006a40`
- `0x18000866c`
- `0x180008730`
- `0x180008b3c`
- `0x18000d5f0`
- `0x18000da80`
- `0x18000de30`
- `0x18000de90`

## string_xrefs

- `0x180008760`: `SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters\Static\Copy0`
- `0x180008757`: `SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters\Static\Copy1`
- `0x18000878c`: `UsingCopyV`
- `0x180008808`: `UsingCopyV`
- `0x1800087e3`: `CopyV`
- `0x180008836`: `SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters\Static\CopyV`
- `0x180008857`: `SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters\Static\CopyV`
- `0x180008869`: `SYSTEM\CurrentControlSet\Services\UWFVOL\PersistentParameters`
- `0x1800088ba`: `SYSTEM\CurrentControlSet\Services\UWFVOL\PersistentParameters\Static\Copy0`
- `0x1800088b1`: `SYSTEM\CurrentControlSet\Services\UWFVOL\PersistentParameters\Static\Copy1`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::Open(HKEY *this, char a2, int a3, char a4, struct CUwfConfiguration *a5)
{
  const unsigned __int16 *v8; // rdi
  HKEY *v9; // rsi
  int SubKey; // ebx
  HKEY phkResult[9]; // [rsp+30h] [rbp-48h] BYREF

  if ( a3 )
  {
    if ( a3 != 1 )
      return 2147942487LL;
    v8 = L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters\\Static\\Copy1";
  }
  else
  {
    v8 = L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters\\Static\\Copy0";
  }
  phkResult[0] = 0;
  if ( !a4 )
  {
    SubKey = CUwfRegKey::Open(
               phkResult,
               HKEY_LOCAL_MACHINE,
               L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\PersistentParameters",
               0x20019u);
    CUwfRegKey::Close(phkResult);
    if ( SubKey != -2147024894 && SubKey != -2147024865 )
    {
      if ( SubKey < 0 )
        return (unsigned int)SubKey;
      if ( a3 )
      {
        if ( a3 != 1 )
          return 2147942487LL;
        v8 = L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\PersistentParameters\\Static\\Copy1";
      }
      else
      {
        v8 = L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\PersistentParameters\\Static\\Copy0";
      }
    }
    return (unsigned int)CUwfStaticConfiguration::Open(this, a2, v8, 0, a5);
  }
  v9 = (HKEY *)((char *)a5 + 32);
  SubKey = CUwfRegKey::OpenSubKey(
             (struct CUwfConfiguration *)((char *)a5 + 32),
             L"UsingCopyV",
             0x20019u,
             (struct CUwfRegKey *)phkResult);
  CUwfRegKey::Close(phkResult);
  if ( SubKey == -2147024894 )
  {
    SubKey = CUwfStaticConfiguration::Open(this, a2, v8, 1, a5);
    if ( SubKey < 0 )
      return (unsigned int)SubKey;
    if ( !a2 )
      return (unsigned int)SubKey;
    SubKey = CUwfStaticConfiguration::CopyTo((CUwfConfiguration **)this, *v9, L"CopyV", 1);
    if ( SubKey < 0 )
      return (unsigned int)SubKey;
    SubKey = CUwfRegKey::CreateSubKey(v9, L"UsingCopyV", 1u, 0x100u, 0, 0);
    if ( SubKey < 0 )
      return (unsigned int)SubKey;
    return (unsigned int)CUwfStaticConfiguration::ReOpen(
                           (CUwfStaticConfiguration *)this,
                           L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters\\Static\\CopyV");
  }
  if ( SubKey >= 0 )
    return (unsigned int)CUwfStaticConfiguration::Open(
                           this,
                           a2,
                           L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters\\Static\\CopyV",
                           1,
                           a5);
  return (unsigned int)SubKey;
}

```

## disassembly

```asm
0x180008730  push    rbx
0x180008732  push    rbp
0x180008733  push    rsi
0x180008734  push    rdi
0x180008735  push    r14
0x180008737  push    r15
0x180008739  sub     rsp, 48h
0x18000873d  mov     esi, r8d
0x180008740  mov     r14b, dl
0x180008743  mov     rbp, rcx
0x180008746  mov     eax, r8d
0x180008749  test    r8d, r8d
0x18000874c  jz      short loc_180008760
0x18000874e  cmp     eax, 1
0x180008751  jnz     loc_1800088AA
0x180008757  lea     rdi, aSystemCurrentc_17; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x18000875e  jmp     short loc_180008767
0x180008760  lea     rdi, aSystemCurrentc_12; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x180008767  mov     [rsp+78h+phkResult], 0
0x180008770  test    r9b, r9b
0x180008773  jz      loc_180008863
0x180008779  mov     r15, [rsp+78h+arg_20]
0x180008781  lea     r9, [rsp+78h+phkResult]; struct CUwfRegKey *
0x180008786  mov     r8d, 20019h; unsigned int
0x18000878c  lea     rdx, aUsingcopyv; "UsingCopyV"
0x180008793  lea     rsi, [r15+20h]
0x180008797  mov     rcx, rsi; this
0x18000879a  call    ?OpenSubKey@CUwfRegKey@@QEAAJPEBGKAEAV1@@Z; CUwfRegKey::OpenSubKey(ushort const *,ulong,CUwfRegKey &)
0x18000879f  lea     rcx, [rsp+78h+phkResult]; this
0x1800087a4  mov     ebx, eax
0x1800087a6  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x1800087ab  cmp     ebx, 80070002h
0x1800087b1  jnz     loc_18000884A
0x1800087b7  mov     r9b, 1; bool
0x1800087ba  mov     [rsp+78h+var_58], r15; struct CUwfConfiguration *
0x1800087bf  mov     r8, rdi; unsigned __int16 *
0x1800087c2  mov     dl, r14b; bool
0x1800087c5  mov     rcx, rbp; this
0x1800087c8  call    ?Open@CUwfStaticConfiguration@@AEAAJ_NPEBG0PEAVCUwfConfiguration@@@Z; CUwfStaticConfiguration::Open(bool,ushort const *,bool,CUwfConfiguration *)
0x1800087cd  mov     ebx, eax
0x1800087cf  test    eax, eax
0x1800087d1  js      loc_1800088E1
0x1800087d7  test    r14b, r14b
0x1800087da  jz      loc_1800088E1
0x1800087e0  mov     rdx, [rsi]; HKEY
0x1800087e3  lea     r8, aCopyv; "CopyV"
0x1800087ea  mov     r9b, 1; bool
0x1800087ed  mov     rcx, rbp; this
0x1800087f0  call    ?CopyTo@CUwfStaticConfiguration@@QEAAJPEAUHKEY__@@PEBG_N@Z; CUwfStaticConfiguration::CopyTo(HKEY__ *,ushort const *,bool)
0x1800087f5  mov     ebx, eax
0x1800087f7  test    eax, eax
0x1800087f9  js      loc_1800088E1
0x1800087ff  mov     [rsp+78h+var_50], 0; struct CUwfRegKey *
0x180008808  lea     rdx, aUsingcopyv; "UsingCopyV"
0x18000880f  mov     r9d, 100h; unsigned int
0x180008815  mov     [rsp+78h+var_58], 0; unsigned int *
0x18000881e  mov     r8d, 1; unsigned int
0x180008824  mov     rcx, rsi; this
0x180008827  call    ?CreateSubKey@CUwfRegKey@@QEAAJPEBGKKPEAKPEAV1@@Z; CUwfRegKey::CreateSubKey(ushort const *,ulong,ulong,ulong *,CUwfRegKey *)
0x18000882c  mov     ebx, eax
0x18000882e  test    eax, eax
0x180008830  js      loc_1800088E1
0x180008836  lea     rdx, aSystemCurrentc_9; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x18000883d  mov     rcx, rbp; this
0x180008840  call    ?ReOpen@CUwfStaticConfiguration@@AEAAJPEBG@Z; CUwfStaticConfiguration::ReOpen(ushort const *)
0x180008845  jmp     loc_1800088DF
0x18000884a  test    ebx, ebx
0x18000884c  js      loc_1800088E1
0x180008852  mov     [rsp+78h+var_58], r15
0x180008857  lea     r8, aSystemCurrentc_9; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x18000885e  mov     r9b, 1
0x180008861  jmp     short loc_1800088D4
0x180008863  mov     r9d, 20019h; samDesired
0x180008869  lea     r8, aSystemCurrentc_15; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x180008870  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180008877  lea     rcx, [rsp+78h+phkResult]; phkResult
0x18000887c  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180008881  lea     rcx, [rsp+78h+phkResult]; this
0x180008886  mov     ebx, eax
0x180008888  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x18000888d  cmp     ebx, 80070002h
0x180008893  jz      short loc_1800088C1
0x180008895  cmp     ebx, 8007001Fh
0x18000889b  jz      short loc_1800088C1
0x18000889d  test    ebx, ebx
0x18000889f  js      short loc_1800088E1
0x1800088a1  test    esi, esi
0x1800088a3  jz      short loc_1800088BA
0x1800088a5  cmp     esi, 1
0x1800088a8  jz      short loc_1800088B1
0x1800088aa  mov     eax, 80070057h
0x1800088af  jmp     short loc_1800088E3
0x1800088b1  lea     rdi, aSystemCurrentc_13; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x1800088b8  jmp     short loc_1800088C1
0x1800088ba  lea     rdi, aSystemCurrentc_18; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x1800088c1  mov     rax, [rsp+78h+arg_20]
0x1800088c9  xor     r9d, r9d; bool
0x1800088cc  mov     [rsp+78h+var_58], rax; struct CUwfConfiguration *
0x1800088d1  mov     r8, rdi; unsigned __int16 *
0x1800088d4  mov     dl, r14b; bool
0x1800088d7  mov     rcx, rbp; this
0x1800088da  call    ?Open@CUwfStaticConfiguration@@AEAAJ_NPEBG0PEAVCUwfConfiguration@@@Z; CUwfStaticConfiguration::Open(bool,ushort const *,bool,CUwfConfiguration *)
0x1800088df  mov     ebx, eax
0x1800088e1  mov     eax, ebx
0x1800088e3  add     rsp, 48h
0x1800088e7  pop     r15
0x1800088e9  pop     r14
0x1800088eb  pop     rdi
0x1800088ec  pop     rsi
0x1800088ed  pop     rbp
0x1800088ee  pop     rbx
0x1800088ef  retn
```
