# ForgetReaderGroup(ulong,ushort const *)

- ea: `0x18002ad8c`
- end: `0x18002afc4`
- name: `?ForgetReaderGroup@@YAXKPEBG@Z`
- size: `568`
- prototype: `void(unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025300`
- `0x1800274a0`

## callees

- `0x180002180`
- `0x180002220`
- `0x1800040d0`
- `0x18000e3d0`
- `0x180010400`
- `0x180013c90`
- `0x180014440`
- `0x180015ac0`
- `0x18002a02c`
- `0x18002a118`
- `0x18002a65c`
- `0x18002ad8c`
- `0x18002ef20`

## string_xrefs

- `0x18002ae48`: `SOFTWARE\Microsoft\Cryptography\Calais\Readers`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
void __fastcall ForgetReaderGroup(int a1, const unsigned __int16 *a2)
{
  int v4; // ecx
  unsigned int i; // esi
  const WCHAR *v6; // r14
  unsigned int *v7; // r9
  unsigned int v8; // r14d
  unsigned __int16 *v9; // rdx
  const unsigned __int16 *v10; // rdx
  ulong v11; // r9d
  unsigned __int16 *v12; // r8
  ulong pExceptionObject; // [rsp+30h] [rbp-B8h] BYREF
  ulong v14; // [rsp+34h] [rbp-B4h] BYREF
  const int *v15; // [rsp+38h] [rbp-B0h] BYREF
  unsigned __int16 *v16; // [rsp+40h] [rbp-A8h]
  __int64 v17; // [rsp+48h] [rbp-A0h]
  const int *v18; // [rsp+50h] [rbp-98h] BYREF
  unsigned __int16 *v19; // [rsp+58h] [rbp-90h]
  __int64 v20; // [rsp+60h] [rbp-88h]
  HKEY hKey[5]; // [rsp+68h] [rbp-80h] BYREF
  int v22; // [rsp+90h] [rbp-58h]
  _DWORD phkResult[20]; // [rsp+98h] [rbp-50h] BYREF
  unsigned __int16 *v24; // [rsp+100h] [rbp+18h] BYREF

  v18 = &CBuffer::`vftable';
  v19 = 0;
  v20 = 0;
  v15 = &CBuffer::`vftable';
  v16 = 0;
  v17 = 0;
  hKey[2] = (HKEY)&CBuffer::`vftable';
  hKey[3] = 0;
  hKey[4] = 0;
  hKey[0] = 0;
  v22 = 1010;
  if ( !*a2 )
  {
    pExceptionObject = -2146435055;
    throw &pExceptionObject;
  }
  v4 = 0;
  while ( dword_180039DB0[4 * v4] != a1 )
  {
    if ( (unsigned int)++v4 >= 2 )
    {
      v14 = -2146435055;
      throw &v14;
    }
  }
  try
  {
    CRegistry::Open(
      hKey,
      *(HKEY *)&dword_180039DB0[4 * v4 + 2],
      L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\Readers",
      0x20019u,
      0xFFFFFFE0);
    CRegistry::Status((CRegistry *)hKey, 0);
  }
  catch ( unsigned long )
  {
    CRegistry::~CRegistry((CRegistry *)hKey);
    goto LABEL_17;
  }
  MStrAdd((struct CBuffer *)&v15, a2);
  for ( i = 0; ; ++i )
  {
    try
    {
      v6 = CRegistry::Subkey((CRegistry *)hKey, i);
    }
    catch ( unsigned long )
    {
      break;
    }
    if ( !v6 )
      break;
    CRegistry::Status((CRegistry *)hKey, 0);
    CRegistry::CRegistry(phkResult, hKey[0], v6, 0x2001Bu, 0xFFFFFFE0);
    v24 = 0;
    CRegistry::GetValue((CRegistry *)phkResult, L"Groups", &v24, v7);
    v8 = MStringCount(v24);
    v9 = (unsigned __int16 *)&WideCharStr;
    if ( HIDWORD(v17) )
      v9 = v16;
    if ( v8 != MStringRemove(v24, v9, (struct CBuffer *)&v18) )
    {
      v12 = (unsigned __int16 *)&WideCharStr;
      if ( HIDWORD(v20) )
        v12 = v19;
      CRegistry::SetMultiStringValue((CRegistry *)phkResult, v10, v12, v11);
    }
    CRegistry::~CRegistry((CRegistry *)phkResult);
  }
  CRegistry::~CRegistry((CRegistry *)hKey);
LABEL_17:
  v15 = &CBuffer::`vftable';
  CBuffer::Clear((CBuffer *)&v15);
  v18 = &CBuffer::`vftable';
  CBuffer::Clear((CBuffer *)&v18);
}

```

## disassembly

```asm
0x18002ad8c  mov     rax, rsp
0x18002ad8f  mov     [rax+8], rbx
0x18002ad93  push    rsi
0x18002ad94  push    rdi
0x18002ad95  push    r14
0x18002ad97  sub     rsp, 0D0h
0x18002ad9e  mov     rsi, rdx
0x18002ada1  mov     edx, ecx
0x18002ada3  lea     rdi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18002adaa  mov     [rsp+0E8h+var_98], rdi
0x18002adaf  xor     ebx, ebx
0x18002adb1  mov     [rsp+0E8h+var_90], rbx
0x18002adb6  mov     [rsp+0E8h+var_88], rbx
0x18002adbb  mov     [rsp+0E8h+var_B0], rdi
0x18002adc0  mov     [rsp+0E8h+var_A8], rbx
0x18002adc5  mov     [rsp+0E8h+var_A0], rbx
0x18002adca  mov     [rax-70h], rdi
0x18002adce  mov     [rax-68h], rbx
0x18002add2  mov     [rax-60h], rbx
0x18002add6  mov     [rax-80h], rbx
0x18002adda  mov     dword ptr [rax-58h], 3F2h
0x18002ade1  cmp     bx, [rsi]
0x18002ade4  jnz     short loc_18002AE00
0x18002ade6  mov     [rsp+0E8h+pExceptionObject], 80100011h
0x18002adee  lea     rdx, _TI1K; pThrowInfo
0x18002adf5  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18002adfa  call    _CxxThrowException_0
0x18002ae00  mov     ecx, ebx
0x18002ae02  lea     r10, dword_180039DB0
0x18002ae09  mov     eax, ecx
0x18002ae0b  add     rax, rax
0x18002ae0e  cmp     [r10+rax*8], edx
0x18002ae12  jz      short loc_18002AE35
0x18002ae14  inc     ecx
0x18002ae16  cmp     ecx, 2
0x18002ae19  jb      short loc_18002AE09
0x18002ae1b  mov     [rsp+0E8h+var_B4], 80100011h
0x18002ae23  lea     rdx, _TI1K; pThrowInfo
0x18002ae2a  lea     rcx, [rsp+0E8h+var_B4]; pExceptionObject
0x18002ae2f  call    _CxxThrowException_0
0x18002ae35  mov     edx, ecx
0x18002ae37  add     rdx, rdx
0x18002ae3a  mov     [rsp+0E8h+dwOptions], 0FFFFFFE0h; dwOptions
0x18002ae42  mov     r9d, 20019h; samDesired
0x18002ae48  lea     r8, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x18002ae4f  mov     rdx, [r10+rdx*8+8]; hKey
0x18002ae54  lea     rcx, [rsp+0E8h+hKey]; phkResult
0x18002ae59  call    ?Open@CRegistry@@QEAAXPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x18002ae5e  xor     edx, edx; int
0x18002ae60  lea     rcx, [rsp+0E8h+hKey]; this
0x18002ae65  call    ?Status@CRegistry@@QEBAJH@Z; CRegistry::Status(int)
0x18002ae6a  nop
0x18002ae6b  mov     rdx, rsi; unsigned __int16 *
0x18002ae6e  lea     rcx, [rsp+0E8h+var_B0]; struct CBuffer *
0x18002ae73  call    ?MStrAdd@@YAKAEAVCBuffer@@PEBG@Z; MStrAdd(CBuffer &,ushort const *)
0x18002ae78  mov     esi, ebx
0x18002ae7a  mov     [rsp+0E8h+arg_8], esi
0x18002ae81  mov     edx, esi; unsigned int
0x18002ae83  lea     rcx, [rsp+0E8h+hKey]; this
0x18002ae88  call    ?Subkey@CRegistry@@QEAAPEBGK@Z; CRegistry::Subkey(ulong)
0x18002ae8d  mov     r14, rax
0x18002ae90  test    r14, r14
0x18002ae93  jz      loc_18002AF5B
0x18002ae99  xor     edx, edx; int
0x18002ae9b  lea     rcx, [rsp+0E8h+hKey]; this
0x18002aea0  call    ?Status@CRegistry@@QEBAJH@Z; CRegistry::Status(int)
0x18002aea5  mov     [rsp+0E8h+dwOptions], 0FFFFFFE0h; dwOptions
0x18002aead  mov     r9d, 2001Bh; samDesired
0x18002aeb3  mov     r8, r14; lpSubKey
0x18002aeb6  mov     rdx, [rsp+0E8h+hKey]; hKey
0x18002aebb  lea     rcx, [rsp+0E8h+phkResult]; phkResult
0x18002aec3  call    ??0CRegistry@@QEAA@PEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z; CRegistry::CRegistry(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x18002aec8  nop
0x18002aec9  mov     [rsp+0E8h+arg_10], rbx
0x18002aed1  lea     r8, [rsp+0E8h+arg_10]; unsigned __int16 **
0x18002aed9  lea     rdx, aGroups_1; "Groups"
0x18002aee0  lea     rcx, [rsp+0E8h+phkResult]; this
0x18002aee8  call    ?GetValue@CRegistry@@QEAAXPEBGPEAPEAGPEAK@Z; CRegistry::GetValue(ushort const *,ushort * *,ulong *)
0x18002aeed  mov     rcx, [rsp+0E8h+arg_10]; unsigned __int16 *
0x18002aef5  call    ?MStringCount@@YAKPEBG@Z; MStringCount(ushort const *)
0x18002aefa  mov     r14d, eax
0x18002aefd  lea     rdx, WideCharStr
0x18002af04  cmp     dword ptr [rsp+0E8h+var_A0+4], ebx
0x18002af08  cmova   rdx, [rsp+0E8h+var_A8]; unsigned __int16 *
0x18002af0e  lea     r8, [rsp+0E8h+var_98]; struct CBuffer *
0x18002af13  mov     rcx, [rsp+0E8h+arg_10]; unsigned __int16 *
0x18002af1b  call    ?MStringRemove@@YAKPEBG0AEAVCBuffer@@@Z; MStringRemove(ushort const *,ushort const *,CBuffer &)
0x18002af20  cmp     r14d, eax
0x18002af23  jz      short loc_18002AF44
0x18002af25  lea     r8, WideCharStr
0x18002af2c  cmp     dword ptr [rsp+0E8h+var_88+4], ebx
0x18002af30  cmova   r8, [rsp+0E8h+var_90]; unsigned __int16 *
0x18002af36  lea     rcx, [rsp+0E8h+phkResult]; this
0x18002af3e  call    ?SetMultiStringValue@CRegistry@@QEBAXPEBG0K@Z; CRegistry::SetMultiStringValue(ushort const *,ushort const *,ulong)
0x18002af43  nop
0x18002af44  lea     rcx, [rsp+0E8h+phkResult]; this
0x18002af4c  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18002af51  nop
0x18002af52  jmp     short loc_18002AF78
0x18002af54  lea     rdi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18002af5b  lea     rcx, [rsp+0E8h+hKey]; this
0x18002af60  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18002af65  nop
0x18002af66  jmp     short loc_18002AF91
0x18002af68  lea     rdi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18002af6f  xor     ebx, ebx
0x18002af71  mov     esi, [rsp+0E8h+arg_8]
0x18002af78  inc     esi
0x18002af7a  jmp     loc_18002AE7A
0x18002af7f  lea     rcx, [rsp+0E8h+hKey]; this
0x18002af84  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18002af89  nop
0x18002af8a  lea     rdi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18002af91  mov     [rsp+0E8h+var_B0], rdi
0x18002af96  lea     rcx, [rsp+0E8h+var_B0]; this
0x18002af9b  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x18002afa0  nop
0x18002afa1  mov     [rsp+0E8h+var_98], rdi
0x18002afa6  lea     rcx, [rsp+0E8h+var_98]; this
0x18002afab  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x18002afb0  mov     rbx, [rsp+0E8h+arg_0]
0x18002afb8  add     rsp, 0D0h
0x18002afbf  pop     r14
0x18002afc1  pop     rdi
0x18002afc2  pop     rsi
0x18002afc3  retn
```
