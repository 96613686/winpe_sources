# CTSDVRSettings::SBE2TMPDirectory(unsigned __int64,ushort *)

- ea: `0x1800567b0`
- end: `0x1800568d8`
- name: `?SBE2TMPDirectory@CTSDVRSettings@@QEAAPEAG_KPEAG@Z`
- size: `296`
- prototype: `unsigned __int16 *(CTSDVRSettings *__hidden this, unsigned __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800a8ba4`

## callees

- `0x180001c00`
- `0x180002b7c`
- `0x180002e68`
- `0x18000624c`
- `0x1800567b0`
- `0x18005f880`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800568a9`
- `KERNEL32!LeaveCriticalSection` at `0x1800568a9`
- `KERNEL32!EnterCriticalSection` at `0x1800567ee`
- `KERNEL32!EnterCriticalSection` at `0x1800567ee`
- `KERNEL32!GetTempPath2W` at `0x180056839`
- `KERNEL32!GetTempPath2W` at `0x180056839`

## string_xrefs

- `0x18005686b`: `\TempSBE`
- `0x180056874`: `TempSBE`

## pseudocode

```c
unsigned __int16 *__fastcall CTSDVRSettings::SBE2TMPDirectory(CTSDVRSettings *this, __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v4; // rbp
  HKEY v6; // rdx
  const unsigned __int16 *v7; // r8
  _WORD *v8; // rbx
  SBECoreUtil *v9; // rcx
  const unsigned __int16 *v10; // r8
  unsigned __int8 *v12; // [rsp+28h] [rbp-50h]
  unsigned __int64 v13; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 v14[4]; // [rsp+38h] [rbp-40h] BYREF

  v13 = 0;
  v4 = 0;
  *(_DWORD *)v14 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v8 = (_WORD *)((char *)this + 64);
  if ( *((_WORD *)this + 32) )
    goto LABEL_12;
  v9 = (SBECoreUtil *)*((_QWORD *)this + 1);
  if ( v9 )
  {
    *(_DWORD *)v14 = 260;
    if ( !SBECoreUtil::GetRegStringValW(v9, v6, v7, v14, (unsigned int *)this + 16, v12) )
      *v8 = 0;
  }
  if ( (*v8 || (*(_DWORD *)v14 = GetTempPath2W(260, (char *)this + 64)) != 0)
    && (int)StringCchLengthW((const unsigned __int16 *)this + 32, 0x104u, &v13) >= 0 )
  {
    if ( !v13 || (v10 = L"\\TempSBE", *((_WORD *)this + v13 + 31) == 92) )
      v10 = L"TempSBE";
    if ( (int)StringCchCatW((unsigned __int16 *)this + 32, 0x104u, v10) >= 0 )
    {
LABEL_12:
      if ( (int)StringCchCopyW(a3, 0x104u, (const unsigned __int16 *)this + 32) >= 0 )
        v4 = a3;
      else
        *a3 = 0;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return v4;
}

```

## disassembly

```asm
0x1800567b0  mov     r11, rsp
0x1800567b3  mov     [r11+10h], rbx
0x1800567b7  mov     [r11+20h], rbp
0x1800567bb  push    rsi
0x1800567bc  push    rdi
0x1800567bd  push    r12
0x1800567bf  push    r14
0x1800567c1  push    r15
0x1800567c3  sub     rsp, 50h
0x1800567c7  mov     rax, cs:__security_cookie
0x1800567ce  xor     rax, rsp
0x1800567d1  mov     [rsp+78h+var_38], rax
0x1800567d6  xor     r15d, r15d
0x1800567d9  mov     rsi, rcx
0x1800567dc  add     rcx, 18h; lpCriticalSection
0x1800567e0  mov     [r11-48h], r15
0x1800567e4  mov     ebp, r15d
0x1800567e7  mov     [r11-40h], r15d
0x1800567eb  mov     rdi, r8
0x1800567ee  call    cs:__imp_EnterCriticalSection
0x1800567f4  lea     rbx, [rsi+40h]
0x1800567f8  mov     r12d, 104h
0x1800567fe  cmp     [rbx], r15w
0x180056802  jnz     loc_18005688A
0x180056808  mov     rcx, [rsi+8]; this
0x18005680c  test    rcx, rcx
0x18005680f  jz      short loc_18005682D
0x180056811  lea     r9, [rsp+78h+var_40]; unsigned __int16 *
0x180056816  mov     dword ptr [rsp+78h+var_40], r12d
0x18005681b  mov     [rsp+78h+var_58], rbx; unsigned int *
0x180056820  call    ?GetRegStringValW@SBECoreUtil@@YAHPEAUHKEY__@@PEBG1PEAKPEAE@Z; SBECoreUtil::GetRegStringValW(HKEY__ *,ushort const *,ushort const *,ulong *,uchar *)
0x180056825  test    eax, eax
0x180056827  jnz     short loc_18005682D
0x180056829  mov     [rbx], r15w
0x18005682d  cmp     [rbx], r15w
0x180056831  jnz     short loc_180056847
0x180056833  mov     rdx, rbx
0x180056836  mov     ecx, r12d
0x180056839  call    cs:__imp_GetTempPath2W
0x18005683f  mov     dword ptr [rsp+78h+var_40], eax
0x180056843  test    eax, eax
0x180056845  jz      short loc_1800568A5
0x180056847  lea     r8, [rsp+78h+var_48]; unsigned __int64 *
0x18005684c  mov     rdx, r12; unsigned __int64
0x18005684f  mov     rcx, rbx; unsigned __int16 *
0x180056852  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180056857  test    eax, eax
0x180056859  js      short loc_1800568A5
0x18005685b  mov     rax, [rsp+78h+var_48]
0x180056860  test    rax, rax
0x180056863  jz      short loc_180056874
0x180056865  cmp     word ptr [rsi+rax*2+3Eh], 5Ch ; '\'
0x18005686b  lea     r8, aTempsbe_0; "\\TempSBE"
0x180056872  jnz     short loc_18005687B
0x180056874  lea     r8, aTempsbe; "TempSBE"
0x18005687b  mov     rdx, r12; unsigned __int64
0x18005687e  mov     rcx, rbx; unsigned __int16 *
0x180056881  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180056886  test    eax, eax
0x180056888  js      short loc_1800568A5
0x18005688a  mov     r8, rbx; unsigned __int16 *
0x18005688d  mov     rdx, r12; unsigned __int64
0x180056890  mov     rcx, rdi; unsigned __int16 *
0x180056893  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180056898  test    eax, eax
0x18005689a  jns     short loc_1800568A2
0x18005689c  mov     [rdi], r15w
0x1800568a0  jmp     short loc_1800568A5
0x1800568a2  mov     rbp, rdi
0x1800568a5  lea     rcx, [rsi+18h]; lpCriticalSection
0x1800568a9  call    cs:__imp_LeaveCriticalSection
0x1800568af  mov     rax, rbp
0x1800568b2  mov     rcx, [rsp+78h+var_38]
0x1800568b7  xor     rcx, rsp; StackCookie
0x1800568ba  call    __security_check_cookie
0x1800568bf  lea     r11, [rsp+78h+var_28]
0x1800568c4  mov     rbx, [r11+38h]
0x1800568c8  mov     rbp, [r11+48h]
0x1800568cc  mov     rsp, r11
0x1800568cf  pop     r15
0x1800568d1  pop     r14
0x1800568d3  pop     r12
0x1800568d5  pop     rdi
0x1800568d6  pop     rsi
0x1800568d7  retn
```
