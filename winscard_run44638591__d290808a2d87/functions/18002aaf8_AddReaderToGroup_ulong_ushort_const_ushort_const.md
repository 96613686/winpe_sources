# AddReaderToGroup(ulong,ushort const *,ushort const *)

- ea: `0x18002aaf8`
- end: `0x18002acaa`
- name: `?AddReaderToGroup@@YAXKPEBG0@Z`
- size: `434`
- prototype: `void(unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024f70`
- `0x1800272a0`

## callees

- `0x180002180`
- `0x180002220`
- `0x1800040d0`
- `0x18000e3d0`
- `0x180010400`
- `0x180013c90`
- `0x180015ac0`
- `0x18002a02c`
- `0x18002a058`
- `0x18002a65c`
- `0x18002aaf8`
- `0x18002ef20`

## string_xrefs

- `0x18002abba`: `SOFTWARE\Microsoft\Cryptography\Calais\Readers`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall AddReaderToGroup(int a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int v6; // ecx
  unsigned int *v7; // r9
  unsigned int v8; // ebx
  unsigned __int16 *v9; // rdi
  unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // rdx
  ulong v12; // r9d
  const int *v13; // [rsp+30h] [rbp-49h] BYREF
  unsigned __int16 *v14; // [rsp+38h] [rbp-41h]
  __int64 v15; // [rsp+40h] [rbp-39h]
  const int *v16; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int16 *v17; // [rsp+50h] [rbp-29h]
  __int64 v18; // [rsp+58h] [rbp-21h]
  HKEY hKey[5]; // [rsp+60h] [rbp-19h] BYREF
  int v20; // [rsp+88h] [rbp+Fh]
  _DWORD phkResult[12]; // [rsp+90h] [rbp+17h] BYREF
  unsigned __int16 *pExceptionObject; // [rsp+F0h] [rbp+77h] BYREF

  v16 = &CBuffer::`vftable';
  v17 = 0;
  v18 = 0;
  v13 = &CBuffer::`vftable';
  v14 = 0;
  v15 = 0;
  hKey[2] = (HKEY)&CBuffer::`vftable';
  hKey[3] = 0;
  hKey[4] = 0;
  hKey[0] = 0;
  v20 = 1010;
  if ( !*a3 )
  {
    LODWORD(pExceptionObject) = -2146435055;
    throw (ulong *)&pExceptionObject;
  }
  v6 = 0;
  while ( dword_180039DB0[4 * v6] != a1 )
  {
    if ( (unsigned int)++v6 >= 2 )
    {
      LODWORD(pExceptionObject) = -2146435055;
      throw (ulong *)&pExceptionObject;
    }
  }
  CRegistry::Open(
    hKey,
    *(HKEY *)&dword_180039DB0[4 * v6 + 2],
    L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\Readers",
    0x20019u,
    0xFFFFFFE0);
  CRegistry::Status((CRegistry *)hKey, 0);
  CRegistry::CRegistry(phkResult, hKey[0], a2, 0x2001Bu, 0xFFFFFFE0);
  MStrAdd((struct CBuffer *)&v13, a3);
  pExceptionObject = 0;
  CRegistry::GetValue((CRegistry *)phkResult, L"Groups", &pExceptionObject, v7);
  v8 = MStringCount(pExceptionObject);
  v9 = (unsigned __int16 *)&WideCharStr;
  v10 = (unsigned __int16 *)&WideCharStr;
  if ( HIDWORD(v15) )
    v10 = v14;
  if ( v8 != MStringMerge(pExceptionObject, v10, (struct CBuffer *)&v16) )
  {
    if ( HIDWORD(v18) )
      v9 = v17;
    CRegistry::SetMultiStringValue((CRegistry *)phkResult, v11, v9, v12);
  }
  CRegistry::~CRegistry((CRegistry *)phkResult);
  CRegistry::~CRegistry((CRegistry *)hKey);
  v13 = &CBuffer::`vftable';
  CBuffer::Clear((CBuffer *)&v13);
  v16 = &CBuffer::`vftable';
  CBuffer::Clear((CBuffer *)&v16);
}

```

## disassembly

```asm
0x18002aaf8  mov     [rsp-8+arg_0], rbx
0x18002aafd  mov     [rsp-8+arg_8], rdi
0x18002ab02  push    rbp
0x18002ab03  push    r14
0x18002ab05  push    r15
0x18002ab07  lea     rbp, [rsp-47h]
0x18002ab0c  sub     rsp, 0C0h
0x18002ab13  mov     rbx, r8
0x18002ab16  mov     rdi, rdx
0x18002ab19  mov     r8d, ecx
0x18002ab1c  lea     r15, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18002ab23  mov     [rbp+57h+var_88], r15
0x18002ab27  xor     r14d, r14d
0x18002ab2a  mov     [rbp+57h+var_80], r14
0x18002ab2e  mov     [rbp+57h+var_78], r14
0x18002ab32  mov     [rbp+57h+var_A0], r15
0x18002ab36  mov     [rbp+57h+var_98], r14
0x18002ab3a  mov     [rbp+57h+var_90], r14
0x18002ab3e  mov     [rbp+57h+var_60], r15
0x18002ab42  mov     [rbp+57h+var_58], r14
0x18002ab46  mov     [rbp+57h+var_50], r14
0x18002ab4a  mov     [rbp+57h+hKey], r14
0x18002ab4e  mov     [rbp+57h+var_48], 3F2h
0x18002ab55  cmp     r14w, [rbx]
0x18002ab59  jnz     short loc_18002AB73
0x18002ab5b  mov     dword ptr [rbp+57h+pExceptionObject], 80100011h
0x18002ab62  lea     rdx, _TI1K; pThrowInfo
0x18002ab69  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002ab6d  call    _CxxThrowException_0
0x18002ab73  mov     ecx, r14d
0x18002ab76  lea     r10, dword_180039DB0
0x18002ab7d  mov     eax, ecx
0x18002ab7f  add     rax, rax
0x18002ab82  cmp     [r10+rax*8], r8d
0x18002ab86  jz      short loc_18002ABA7
0x18002ab88  inc     ecx
0x18002ab8a  cmp     ecx, 2
0x18002ab8d  jb      short loc_18002AB7D
0x18002ab8f  mov     dword ptr [rbp+57h+pExceptionObject], 80100011h
0x18002ab96  lea     rdx, _TI1K; pThrowInfo
0x18002ab9d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002aba1  call    _CxxThrowException_0
0x18002aba7  mov     edx, ecx
0x18002aba9  add     rdx, rdx
0x18002abac  mov     [rsp+0D0h+dwOptions], 0FFFFFFE0h; dwOptions
0x18002abb4  mov     r9d, 20019h; samDesired
0x18002abba  lea     r8, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x18002abc1  mov     rdx, [r10+rdx*8+8]; hKey
0x18002abc6  lea     rcx, [rbp+57h+hKey]; phkResult
0x18002abca  call    ?Open@CRegistry@@QEAAXPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x18002abcf  xor     edx, edx; int
0x18002abd1  lea     rcx, [rbp+57h+hKey]; this
0x18002abd5  call    ?Status@CRegistry@@QEBAJH@Z; CRegistry::Status(int)
0x18002abda  mov     [rsp+0D0h+dwOptions], 0FFFFFFE0h; dwOptions
0x18002abe2  mov     r9d, 2001Bh; samDesired
0x18002abe8  mov     r8, rdi; lpSubKey
0x18002abeb  mov     rdx, [rbp+57h+hKey]; hKey
0x18002abef  lea     rcx, [rbp+57h+phkResult]; phkResult
0x18002abf3  call    ??0CRegistry@@QEAA@PEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z; CRegistry::CRegistry(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x18002abf8  nop
0x18002abf9  mov     rdx, rbx; unsigned __int16 *
0x18002abfc  lea     rcx, [rbp+57h+var_A0]; struct CBuffer *
0x18002ac00  call    ?MStrAdd@@YAKAEAVCBuffer@@PEBG@Z; MStrAdd(CBuffer &,ushort const *)
0x18002ac05  mov     [rbp+57h+pExceptionObject], r14
0x18002ac09  lea     r8, [rbp+57h+pExceptionObject]; unsigned __int16 **
0x18002ac0d  lea     rdx, aGroups_1; "Groups"
0x18002ac14  lea     rcx, [rbp+57h+phkResult]; this
0x18002ac18  call    ?GetValue@CRegistry@@QEAAXPEBGPEAPEAGPEAK@Z; CRegistry::GetValue(ushort const *,ushort * *,ulong *)
0x18002ac1d  mov     rcx, [rbp+57h+pExceptionObject]; unsigned __int16 *
0x18002ac21  call    ?MStringCount@@YAKPEBG@Z; MStringCount(ushort const *)
0x18002ac26  mov     ebx, eax
0x18002ac28  lea     rdi, WideCharStr
0x18002ac2f  mov     rdx, rdi
0x18002ac32  cmp     dword ptr [rbp+57h+var_90+4], r14d
0x18002ac36  cmova   rdx, [rbp+57h+var_98]; unsigned __int16 *
0x18002ac3b  lea     r8, [rbp+57h+var_88]; struct CBuffer *
0x18002ac3f  mov     rcx, [rbp+57h+pExceptionObject]; unsigned __int16 *
0x18002ac43  call    ?MStringMerge@@YAKPEBG0AEAVCBuffer@@@Z; MStringMerge(ushort const *,ushort const *,CBuffer &)
0x18002ac48  cmp     ebx, eax
0x18002ac4a  jz      short loc_18002AC62
0x18002ac4c  cmp     dword ptr [rbp+57h+var_78+4], r14d
0x18002ac50  cmova   rdi, [rbp+57h+var_80]
0x18002ac55  mov     r8, rdi; unsigned __int16 *
0x18002ac58  lea     rcx, [rbp+57h+phkResult]; this
0x18002ac5c  call    ?SetMultiStringValue@CRegistry@@QEBAXPEBG0K@Z; CRegistry::SetMultiStringValue(ushort const *,ushort const *,ulong)
0x18002ac61  nop
0x18002ac62  lea     rcx, [rbp+57h+phkResult]; this
0x18002ac66  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18002ac6b  nop
0x18002ac6c  lea     rcx, [rbp+57h+hKey]; this
0x18002ac70  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18002ac75  nop
0x18002ac76  mov     [rbp+57h+var_A0], r15
0x18002ac7a  lea     rcx, [rbp+57h+var_A0]; this
0x18002ac7e  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x18002ac83  nop
0x18002ac84  mov     [rbp+57h+var_88], r15
0x18002ac88  lea     rcx, [rbp+57h+var_88]; this
0x18002ac8c  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x18002ac91  lea     r11, [rsp+0D0h+var_10]
0x18002ac99  mov     rbx, [r11+20h]
0x18002ac9d  mov     rdi, [r11+28h]
0x18002aca1  mov     rsp, r11
0x18002aca4  pop     r15
0x18002aca6  pop     r14
0x18002aca8  pop     rbp
0x18002aca9  retn
```
