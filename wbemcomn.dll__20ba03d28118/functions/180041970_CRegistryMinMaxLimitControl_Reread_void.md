# CRegistryMinMaxLimitControl::Reread(void)

- ea: `0x180041970`
- end: `0x180041add`
- name: `?Reread@CRegistryMinMaxLimitControl@@QEAAJXZ`
- size: `365`
- prototype: `__int64 __fastcall(CRegistryMinMaxLimitControl *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000eea0`
- `0x18000f380`
- `0x18000f4c0`
- `0x180010240`
- `0x180014120`
- `0x180016730`
- `0x180041970`
- `0x180041afc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041ab6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041ab6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRegistryMinMaxLimitControl::Reread(CRegistryMinMaxLimitControl *this)
{
  int v2; // edx
  int v3; // r8d
  unsigned int v4; // ebx
  unsigned int *v5; // rdi
  unsigned int v6; // r15d
  unsigned int v7; // r14d
  unsigned int v8; // esi
  _BYTE v10[20]; // [rsp+30h] [rbp-20h] BYREF
  int v11; // [rsp+44h] [rbp-Ch]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v13; // [rsp+88h] [rbp+38h] BYREF
  unsigned int v14; // [rsp+90h] [rbp+40h] BYREF

  Registry::Registry((Registry *)v10, *((const unsigned __int16 **)this + 11), 3u);
  if ( v11 )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0xFFFFFFFF);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v2, v3, *((_QWORD *)this + 11), *((_QWORD *)this + 4), v11);
    }
    v4 = -2147217407;
  }
  else
  {
    LODWORD(lpCriticalSection) = 0;
    v13 = 0;
    v14 = 0;
    v5 = (unsigned int *)((char *)this + 16);
    if ( (unsigned int)Registry::GetDWORDStr(
                         (Registry *)v10,
                         *((const unsigned __int16 **)this + 12),
                         (unsigned int *)&lpCriticalSection) )
    {
      Registry::SetDWORDStr((Registry *)v10, *((const unsigned __int16 **)this + 12), *v5);
      v6 = *v5;
    }
    else
    {
      v6 = (unsigned int)lpCriticalSection;
    }
    if ( (unsigned int)Registry::GetDWORDStr((Registry *)v10, *((const unsigned __int16 **)this + 13), &v13) )
    {
      Registry::SetDWORDStr((Registry *)v10, *((const unsigned __int16 **)this + 13), *((_DWORD *)this + 5));
      v7 = *((_DWORD *)this + 5);
    }
    else
    {
      v7 = v13;
    }
    if ( (unsigned int)Registry::GetDWORDStr((Registry *)v10, *((const unsigned __int16 **)this + 14), &v14) )
    {
      Registry::SetDWORDStr((Registry *)v10, *((const unsigned __int16 **)this + 14), *((_DWORD *)this + 6));
      v8 = *((_DWORD *)this + 6);
    }
    else
    {
      v8 = v14;
    }
    CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)this + 48));
    *v5 = v6;
    *((_DWORD *)this + 5) = v7;
    *((_DWORD *)this + 6) = v8;
    LeaveCriticalSection(lpCriticalSection);
    v4 = 0;
  }
  Registry::~Registry((Registry *)v10);
  return v4;
}

```

## disassembly

```asm
0x180041970  mov     [rsp-28h+arg_18], rbx
0x180041975  push    rbp
0x180041976  push    rsi
0x180041977  push    rdi
0x180041978  push    r14
0x18004197a  push    r15
0x18004197c  mov     rbp, rsp
0x18004197f  sub     rsp, 50h
0x180041983  mov     rbx, rcx
0x180041986  mov     r8d, 3; unsigned int
0x18004198c  mov     rdx, [rcx+58h]; unsigned __int16 *
0x180041990  lea     rcx, [rbp+var_20]; this
0x180041994  call    ??0Registry@@QEAA@PEBGK@Z; Registry::Registry(ushort const *,ulong)
0x180041999  nop
0x18004199a  cmp     [rbp+var_C], 0
0x18004199e  jz      short loc_1800419F5
0x1800419a0  or      edx, 0FFFFFFFFh; int
0x1800419a3  lea     rcx, qword_18006A9C0; this
0x1800419aa  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800419af  lea     rax, WPP_GLOBAL_Control
0x1800419b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800419bd  cmp     rcx, rax
0x1800419c0  jz      short loc_1800419EB
0x1800419c2  test    byte ptr [rcx+1Ch], 1
0x1800419c6  jz      short loc_1800419EB
0x1800419c8  cmp     byte ptr [rcx+19h], 2
0x1800419cc  jb      short loc_1800419EB
0x1800419ce  mov     eax, [rbp+var_C]
0x1800419d1  mov     [rsp+50h+var_28], eax
0x1800419d5  mov     rax, [rbx+20h]
0x1800419d9  mov     [rsp+50h+var_30], rax
0x1800419de  mov     r9, [rbx+58h]
0x1800419e2  mov     rcx, [rcx+10h]
0x1800419e6  call    WPP_SF_SSd
0x1800419eb  mov     ebx, 80041001h
0x1800419f0  jmp     loc_180041ABE
0x1800419f5  mov     dword ptr [rbp+lpCriticalSection], 0
0x1800419fc  mov     [rbp+arg_8], 0
0x180041a03  mov     [rbp+arg_10], 0
0x180041a0a  lea     rdi, [rbx+10h]
0x180041a0e  lea     r8, [rbp+lpCriticalSection]; unsigned int *
0x180041a12  mov     rdx, [rbx+60h]; unsigned __int16 *
0x180041a16  lea     rcx, [rbp+var_20]; this
0x180041a1a  call    ?GetDWORDStr@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORDStr(ushort const *,ulong *)
0x180041a1f  test    eax, eax
0x180041a21  jz      short loc_180041A38
0x180041a23  mov     r8d, [rdi]; unsigned int
0x180041a26  mov     rdx, [rbx+60h]; unsigned __int16 *
0x180041a2a  lea     rcx, [rbp+var_20]; this
0x180041a2e  call    ?SetDWORDStr@Registry@@QEAAHPEBGK@Z; Registry::SetDWORDStr(ushort const *,ulong)
0x180041a33  mov     r15d, [rdi]
0x180041a36  jmp     short loc_180041A3C
0x180041a38  mov     r15d, dword ptr [rbp+lpCriticalSection]
0x180041a3c  lea     r8, [rbp+arg_8]; unsigned int *
0x180041a40  mov     rdx, [rbx+68h]; unsigned __int16 *
0x180041a44  lea     rcx, [rbp+var_20]; this
0x180041a48  call    ?GetDWORDStr@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORDStr(ushort const *,ulong *)
0x180041a4d  test    eax, eax
0x180041a4f  jz      short loc_180041A68
0x180041a51  mov     r8d, [rbx+14h]; unsigned int
0x180041a55  mov     rdx, [rbx+68h]; unsigned __int16 *
0x180041a59  lea     rcx, [rbp+var_20]; this
0x180041a5d  call    ?SetDWORDStr@Registry@@QEAAHPEBGK@Z; Registry::SetDWORDStr(ushort const *,ulong)
0x180041a62  mov     r14d, [rbx+14h]
0x180041a66  jmp     short loc_180041A6C
0x180041a68  mov     r14d, [rbp+arg_8]
0x180041a6c  lea     r8, [rbp+arg_10]; unsigned int *
0x180041a70  mov     rdx, [rbx+70h]; unsigned __int16 *
0x180041a74  lea     rcx, [rbp+var_20]; this
0x180041a78  call    ?GetDWORDStr@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORDStr(ushort const *,ulong *)
0x180041a7d  test    eax, eax
0x180041a7f  jz      short loc_180041A97
0x180041a81  mov     r8d, [rbx+18h]; unsigned int
0x180041a85  mov     rdx, [rbx+70h]; unsigned __int16 *
0x180041a89  lea     rcx, [rbp+var_20]; this
0x180041a8d  call    ?SetDWORDStr@Registry@@QEAAHPEBGK@Z; Registry::SetDWORDStr(ushort const *,ulong)
0x180041a92  mov     esi, [rbx+18h]
0x180041a95  jmp     short loc_180041A9A
0x180041a97  mov     esi, [rbp+arg_10]
0x180041a9a  lea     rdx, [rbx+30h]; struct _RTL_CRITICAL_SECTION *
0x180041a9e  lea     rcx, [rbp+lpCriticalSection]; this
0x180041aa2  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180041aa7  nop
0x180041aa8  mov     [rdi], r15d
0x180041aab  mov     [rbx+14h], r14d
0x180041aaf  mov     [rbx+18h], esi
0x180041ab2  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180041ab6  call    cs:__imp_LeaveCriticalSection
0x180041abc  xor     ebx, ebx
0x180041abe  lea     rcx, [rbp+var_20]; this
0x180041ac2  call    ??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x180041ac7  mov     eax, ebx
0x180041ac9  mov     rbx, [rsp+50h+arg_18]
0x180041ad1  add     rsp, 50h
0x180041ad5  pop     r15
0x180041ad7  pop     r14
0x180041ad9  pop     rdi
0x180041ada  pop     rsi
0x180041adb  pop     rbp
0x180041adc  retn
```
