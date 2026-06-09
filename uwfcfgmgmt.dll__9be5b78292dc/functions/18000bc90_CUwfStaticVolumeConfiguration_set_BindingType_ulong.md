# CUwfStaticVolumeConfiguration::set_BindingType(ulong)

- ea: `0x18000bc90`
- end: `0x18000bded`
- name: `?set_BindingType@CUwfStaticVolumeConfiguration@@QEAAJK@Z`
- size: `349`
- prototype: `__int64 __fastcall(CUwfConfiguration **this, unsigned int)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180006c80`
- `0x180009100`
- `0x18001a4e0`

## callees

- `0x1800054d0`
- `0x1800071d0`
- `0x1800072b0`
- `0x180009758`
- `0x180009f38`
- `0x18000a150`
- `0x18000bc90`
- `0x18000e320`
- `0x180011490`
- `0x18001afe2`
- `0x18001b020`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000bdc2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000bdc2`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::set_BindingType(CUwfConfiguration **this, unsigned int a2)
{
  unsigned __int16 *v2; // rsi
  int MediaType; // ebx
  int updated; // eax
  int v7; // eax
  _MEDIA_TYPE v9; // [rsp+30h] [rbp-59h] BYREF
  unsigned __int16 *v10; // [rsp+38h] [rbp-51h] BYREF
  WCHAR FileName[56]; // [rsp+40h] [rbp-49h] BYREF

  v2 = 0;
  v10 = 0;
  memset_0(FileName, 0, 0x64u);
  v9 = Unknown;
  if ( *((_BYTE *)this + 9) )
  {
    MediaType = -2147024891;
  }
  else
  {
    updated = CUwfConfiguration::UpdateDWORDValue(this[3], (struct CUwfRegKey *)(this + 2), L"Binding", a2, 1);
    MediaType = updated;
    if ( updated == 1 )
    {
      MediaType = 0;
    }
    else if ( !updated )
    {
      if ( (int)CUwfRegKey::QuerySzValue((HKEY *)this + 2, L"VolumeName", &v10) >= 0 )
      {
        v2 = v10;
      }
      else
      {
        MediaType = CUwfRegKey::QuerySzValue((HKEY *)this + 2, L"DriveLetter", &v10);
        v2 = v10;
        if ( MediaType < 0 )
          goto LABEL_18;
      }
      MediaType = StringCchPrintfW(FileName, 0x32u, L"\\\\?\\%s", v2);
      if ( MediaType >= 0 )
      {
        MediaType = VolumeGetMediaType(FileName, &v9);
        if ( MediaType >= 0 )
        {
          if ( v9 == FixedMedia )
          {
            if ( a2 )
            {
              CUwfStaticVolumeConfiguration::DeleteLooseBindingConfiguration((CUwfStaticVolumeConfiguration *)this);
              v7 = CUwfStaticVolumeConfiguration::SetTightBindingConfiguration(
                     (CUwfStaticVolumeConfiguration *)this,
                     FileName);
            }
            else
            {
              CUwfStaticVolumeConfiguration::DeleteTightBindingConfiguration((CUwfStaticVolumeConfiguration *)this);
              v7 = CUwfStaticVolumeConfiguration::SetLooseBindingConfiguration(
                     (CUwfStaticVolumeConfiguration *)this,
                     FileName);
            }
            MediaType = v7;
          }
          else
          {
            MediaType = -2147024846;
          }
        }
      }
    }
  }
LABEL_18:
  operator delete[](v2);
  return (unsigned int)MediaType;
}

```

## disassembly

```asm
0x18000bc90  mov     [rsp-8+arg_10], rbx
0x18000bc95  push    rbp
0x18000bc96  push    rsi
0x18000bc97  push    rdi
0x18000bc98  push    r14
0x18000bc9a  push    r15
0x18000bc9c  lea     rbp, [rsp-37h]
0x18000bca1  sub     rsp, 0C0h
0x18000bca8  mov     rax, cs:__security_cookie
0x18000bcaf  xor     rax, rsp
0x18000bcb2  mov     [rbp+57h+var_30], rax
0x18000bcb6  xor     esi, esi
0x18000bcb8  mov     r15d, edx
0x18000bcbb  mov     rdi, rcx
0x18000bcbe  mov     [rbp+57h+var_A8], rsi
0x18000bcc2  xor     edx, edx; Val
0x18000bcc4  lea     rcx, [rbp+57h+FileName]; void *
0x18000bcc8  lea     r8d, [rsi+64h]; Size
0x18000bccc  call    memset_0
0x18000bcd1  mov     [rbp+57h+var_B0], esi
0x18000bcd4  cmp     [rdi+9], sil
0x18000bcd8  jz      short loc_18000BCE4
0x18000bcda  mov     ebx, 80070005h
0x18000bcdf  jmp     loc_18000BDBF
0x18000bce4  mov     rcx, [rdi+18h]; this
0x18000bce8  lea     r14, [rdi+10h]
0x18000bcec  mov     rdx, r14; struct CUwfRegKey *
0x18000bcef  mov     [rsp+0E0h+var_C0], 1; bool
0x18000bcf4  mov     r9d, r15d; unsigned int
0x18000bcf7  lea     r8, aBinding; "Binding"
0x18000bcfe  call    ?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z; CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)
0x18000bd03  mov     ebx, eax
0x18000bd05  cmp     eax, 1
0x18000bd08  jnz     short loc_18000BD11
0x18000bd0a  xor     ebx, ebx
0x18000bd0c  jmp     loc_18000BDBF
0x18000bd11  test    eax, eax
0x18000bd13  jnz     loc_18000BDBF
0x18000bd19  lea     r8, [rbp+57h+var_A8]; unsigned __int16 **
0x18000bd1d  mov     rcx, r14; this
0x18000bd20  lea     rdx, aVolumename; "VolumeName"
0x18000bd27  call    ?QuerySzValue@CUwfRegKey@@QEAAJPEBGPEAPEAG@Z; CUwfRegKey::QuerySzValue(ushort const *,ushort * *)
0x18000bd2c  test    eax, eax
0x18000bd2e  jns     short loc_18000BD4F
0x18000bd30  lea     r8, [rbp+57h+var_A8]; unsigned __int16 **
0x18000bd34  mov     rcx, r14; this
0x18000bd37  lea     rdx, aDriveletter; "DriveLetter"
0x18000bd3e  call    ?QuerySzValue@CUwfRegKey@@QEAAJPEBGPEAPEAG@Z; CUwfRegKey::QuerySzValue(ushort const *,ushort * *)
0x18000bd43  mov     ebx, eax
0x18000bd45  mov     rsi, [rbp+57h+var_A8]
0x18000bd49  test    eax, eax
0x18000bd4b  jns     short loc_18000BD53
0x18000bd4d  jmp     short loc_18000BDBF
0x18000bd4f  mov     rsi, [rbp+57h+var_A8]
0x18000bd53  mov     r9, rsi
0x18000bd56  lea     r8, aS; "\\\\?\\%s"
0x18000bd5d  mov     edx, 32h ; '2'; unsigned __int64
0x18000bd62  lea     rcx, [rbp+57h+FileName]; unsigned __int16 *
0x18000bd66  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000bd6b  mov     ebx, eax
0x18000bd6d  test    eax, eax
0x18000bd6f  js      short loc_18000BDBF
0x18000bd71  lea     rdx, [rbp+57h+var_B0]; enum _MEDIA_TYPE *
0x18000bd75  lea     rcx, [rbp+57h+FileName]; lpFileName
0x18000bd79  call    ?VolumeGetMediaType@@YAJPEBGPEAW4_MEDIA_TYPE@@@Z; VolumeGetMediaType(ushort const *,_MEDIA_TYPE *)
0x18000bd7e  mov     ebx, eax
0x18000bd80  test    eax, eax
0x18000bd82  js      short loc_18000BDBF
0x18000bd84  cmp     [rbp+57h+var_B0], 0Ch
0x18000bd88  jz      short loc_18000BD91
0x18000bd8a  mov     ebx, 80070032h
0x18000bd8f  jmp     short loc_18000BDBF
0x18000bd91  mov     rcx, rdi; this
0x18000bd94  test    r15d, r15d
0x18000bd97  jnz     short loc_18000BDAC
0x18000bd99  call    ?DeleteTightBindingConfiguration@CUwfStaticVolumeConfiguration@@AEAAXXZ; CUwfStaticVolumeConfiguration::DeleteTightBindingConfiguration(void)
0x18000bd9e  lea     rdx, [rbp+57h+FileName]; unsigned __int16 *
0x18000bda2  mov     rcx, rdi; this
0x18000bda5  call    ?SetLooseBindingConfiguration@CUwfStaticVolumeConfiguration@@AEAAJPEBG@Z; CUwfStaticVolumeConfiguration::SetLooseBindingConfiguration(ushort const *)
0x18000bdaa  jmp     short loc_18000BDBD
0x18000bdac  call    ?DeleteLooseBindingConfiguration@CUwfStaticVolumeConfiguration@@AEAAXXZ; CUwfStaticVolumeConfiguration::DeleteLooseBindingConfiguration(void)
0x18000bdb1  lea     rdx, [rbp+57h+FileName]; lpFileName
0x18000bdb5  mov     rcx, rdi; this
0x18000bdb8  call    ?SetTightBindingConfiguration@CUwfStaticVolumeConfiguration@@AEAAJPEBG@Z; CUwfStaticVolumeConfiguration::SetTightBindingConfiguration(ushort const *)
0x18000bdbd  mov     ebx, eax
0x18000bdbf  mov     rcx, rsi
0x18000bdc2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000bdc8  mov     eax, ebx
0x18000bdca  mov     rcx, [rbp+57h+var_30]
0x18000bdce  xor     rcx, rsp; StackCookie
0x18000bdd1  call    __security_check_cookie
0x18000bdd6  mov     rbx, [rsp+0E0h+arg_10]
0x18000bdde  add     rsp, 0C0h
0x18000bde5  pop     r15
0x18000bde7  pop     r14
0x18000bde9  pop     rdi
0x18000bdea  pop     rsi
0x18000bdeb  pop     rbp
0x18000bdec  retn
```
