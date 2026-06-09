# CUwfStaticConfiguration::get_IsNoFileExclusion(bool *)

- ea: `0x18000ac60`
- end: `0x18000ade4`
- name: `?get_IsNoFileExclusion@CUwfStaticConfiguration@@QEAAJPEA_N@Z`
- size: `388`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callees

- `0x180001390`
- `0x180008300`
- `0x180008cf0`
- `0x18000ac60`
- `0x18000e0f0`
- `0x18000e170`
- `0x18001c010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ad79`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000adc7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ad79`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000adc7`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::get_IsNoFileExclusion(CUwfStaticConfiguration *this, bool *a2)
{
  struct _MULTISZ *v4; // rsi
  int v5; // edi
  char *v6; // r15
  unsigned int i; // r14d
  char *v8; // rbx
  char *v9; // rax
  void (__fastcall ***v10)(_QWORD, __int64); // rcx
  unsigned int v12; // [rsp+78h] [rbp+10h] BYREF
  struct _MULTISZ *v13; // [rsp+80h] [rbp+18h] BYREF

  *a2 = 1;
  v12 = 0;
  v4 = 0;
  v13 = 0;
  v5 = CUwfRegKey::QueryDWORDValue((CUwfStaticConfiguration *)((char *)this + 24), L"NumVolumes", &v12);
  if ( v5 >= 0 )
  {
    v6 = 0;
    for ( i = 0; i < v12; v13 = 0 )
    {
      CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(this);
      v8 = (char *)*((_QWORD *)this + 5);
      v5 = 0;
      if ( v8 )
      {
        v10 = 0;
      }
      else
      {
        v9 = (char *)operator new(0x28u);
        v8 = v9;
        if ( !v9 )
        {
          v5 = -2147024882;
          break;
        }
        *(_WORD *)(v9 + 9) = 1;
        *(_QWORD *)v9 = &CUwfStaticVolumeConfiguration::`vftable';
        *((_DWORD *)v9 + 3) = -1;
        *((_QWORD *)v9 + 2) = 0;
        *((_QWORD *)v9 + 3) = 0;
        *((_QWORD *)v9 + 4) = 0;
        v5 = CUwfStaticVolumeConfiguration::Initialize(
               (CUwfStaticVolumeConfiguration *)v9,
               *((HKEY *)this + 3),
               i,
               *((_BYTE *)this + 8),
               *((struct CUwfConfiguration **)this + 4),
               this);
        v10 = (void (__fastcall ***)(_QWORD, __int64))v8;
        if ( v5 < 0 )
        {
LABEL_17:
          (**v10)(v10, 1);
          break;
        }
        *((_QWORD *)this + 5) = v8;
      }
      if ( *((_DWORD *)v8 + 3) == i )
      {
        v6 = v8;
      }
      else
      {
        v5 = -2147024891;
        if ( v10 )
          goto LABEL_17;
      }
      if ( v5 < 0 )
        break;
      CUwfRegKey::QueryMultiSzValue((CUwfRegKey *)(v6 + 16), L"FileExceptionsUserDefined", &v13);
      v4 = v13;
      if ( *((_DWORD *)v13 + 6) )
      {
        *a2 = 0;
        break;
      }
      operator delete[](v13);
      v4 = 0;
      ++i;
    }
  }
  CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(this);
  if ( v4 )
    operator delete[](v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000ac60  mov     rax, rsp
0x18000ac63  mov     [rax+8], rbx
0x18000ac67  push    rbp
0x18000ac68  push    rsi
0x18000ac69  push    rdi
0x18000ac6a  push    r12
0x18000ac6c  push    r13
0x18000ac6e  push    r14
0x18000ac70  push    r15
0x18000ac72  sub     rsp, 30h
0x18000ac76  mov     r12, rdx
0x18000ac79  mov     byte ptr [rdx], 1
0x18000ac7c  mov     rbp, rcx
0x18000ac7f  mov     dword ptr [rax+10h], 0
0x18000ac86  xor     esi, esi
0x18000ac88  lea     rdx, aNumvolumes; "NumVolumes"
0x18000ac8f  add     rcx, 18h; this
0x18000ac93  mov     [rax+18h], rsi
0x18000ac97  lea     r8, [rax+10h]; unsigned int *
0x18000ac9b  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x18000aca0  mov     edi, eax
0x18000aca2  test    eax, eax
0x18000aca4  js      loc_18000ADB7
0x18000acaa  xor     r15d, r15d
0x18000acad  xor     r14d, r14d
0x18000acb0  cmp     [rsp+68h+arg_8], esi
0x18000acb4  jbe     loc_18000ADB7
0x18000acba  mov     rcx, rbp; this
0x18000acbd  call    ?ReleaseStaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(void)
0x18000acc2  mov     rbx, [rbp+28h]
0x18000acc6  xor     edi, edi
0x18000acc8  test    rbx, rbx
0x18000accb  jnz     short loc_18000AD34
0x18000accd  lea     ecx, [rbx+28h]; Size
0x18000acd0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000acd5  mov     rbx, rax
0x18000acd8  test    rax, rax
0x18000acdb  jz      loc_18000AD99
0x18000ace1  mov     word ptr [rbx+9], 1
0x18000ace7  lea     rax, ??_7CUwfStaticVolumeConfiguration@@6B@; const CUwfStaticVolumeConfiguration::`vftable'
0x18000acee  mov     [rbx], rax
0x18000acf1  mov     r8d, r14d; unsigned int
0x18000acf4  mov     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x18000acfb  mov     rcx, rbx; this
0x18000acfe  mov     [rbx+10h], rdi
0x18000ad02  mov     [rbx+18h], rdi
0x18000ad06  mov     [rbx+20h], rdi
0x18000ad0a  mov     rax, [rbp+20h]
0x18000ad0e  mov     r9b, [rbp+8]; bool
0x18000ad12  mov     rdx, [rbp+18h]; HKEY
0x18000ad16  mov     [rsp+68h+var_40], rbp; struct CUwfStaticConfiguration *
0x18000ad1b  mov     [rsp+68h+var_48], rax; struct CUwfConfiguration *
0x18000ad20  call    ?Initialize@CUwfStaticVolumeConfiguration@@QEAAJPEAUHKEY__@@K_NPEAVCUwfConfiguration@@PEAVCUwfStaticConfiguration@@@Z; CUwfStaticVolumeConfiguration::Initialize(HKEY__ *,ulong,bool,CUwfConfiguration *,CUwfStaticConfiguration *)
0x18000ad25  mov     edi, eax
0x18000ad27  mov     rcx, rbx
0x18000ad2a  test    eax, eax
0x18000ad2c  js      short loc_18000ADA7
0x18000ad2e  mov     [rbp+28h], rbx
0x18000ad32  jmp     short loc_18000AD37
0x18000ad34  mov     rcx, rdi
0x18000ad37  cmp     [rbx+0Ch], r14d
0x18000ad3b  jnz     short loc_18000AD42
0x18000ad3d  mov     r15, rbx
0x18000ad40  jmp     short loc_18000AD4C
0x18000ad42  mov     edi, 80070005h
0x18000ad47  test    rcx, rcx
0x18000ad4a  jnz     short loc_18000ADA7
0x18000ad4c  test    edi, edi
0x18000ad4e  js      short loc_18000ADB7
0x18000ad50  lea     rcx, [r15+10h]; this
0x18000ad54  lea     r8, [rsp+68h+arg_10]; struct _MULTISZ **
0x18000ad5c  lea     rdx, Value; "FileExceptionsUserDefined"
0x18000ad63  call    ?QueryMultiSzValue@CUwfRegKey@@QEAAJPEBGPEAPEAU_MULTISZ@@@Z; CUwfRegKey::QueryMultiSzValue(ushort const *,_MULTISZ * *)
0x18000ad68  mov     rsi, [rsp+68h+arg_10]
0x18000ad70  cmp     dword ptr [rsi+18h], 0
0x18000ad74  ja      short loc_18000ADA0
0x18000ad76  mov     rcx, rsi
0x18000ad79  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000ad7f  xor     esi, esi
0x18000ad81  inc     r14d
0x18000ad84  mov     [rsp+68h+arg_10], rsi
0x18000ad8c  cmp     r14d, [rsp+68h+arg_8]
0x18000ad91  jb      loc_18000ACBA
0x18000ad97  jmp     short loc_18000ADB7
0x18000ad99  mov     edi, 8007000Eh
0x18000ad9e  jmp     short loc_18000ADB7
0x18000ada0  mov     byte ptr [r12], 0
0x18000ada5  jmp     short loc_18000ADB7
0x18000ada7  mov     rax, [rcx]
0x18000adaa  mov     edx, 1
0x18000adaf  mov     rax, [rax]
0x18000adb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adb7  mov     rcx, rbp; this
0x18000adba  call    ?ReleaseStaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(void)
0x18000adbf  test    rsi, rsi
0x18000adc2  jz      short loc_18000ADCD
0x18000adc4  mov     rcx, rsi
0x18000adc7  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000adcd  mov     rbx, [rsp+68h+arg_0]
0x18000add2  mov     eax, edi
0x18000add4  add     rsp, 30h
0x18000add8  pop     r15
0x18000adda  pop     r14
0x18000addc  pop     r13
0x18000adde  pop     r12
0x18000ade0  pop     rdi
0x18000ade1  pop     rsi
0x18000ade2  pop     rbp
0x18000ade3  retn
```
