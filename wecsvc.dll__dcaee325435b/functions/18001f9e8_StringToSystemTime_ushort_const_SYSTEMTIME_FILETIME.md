# StringToSystemTime(ushort const *,_SYSTEMTIME &,_FILETIME *)

- ea: `0x18001f9e8`
- end: `0x18001fb35`
- name: `?StringToSystemTime@@YA_NPEBGAEAU_SYSTEMTIME@@PEAU_FILETIME@@@Z`
- size: `333`
- prototype: `char __fastcall(const unsigned __int16 *, struct _SYSTEMTIME *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016098`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x18001f9e8`

## import_xrefs

- `msvcrt!swscanf_s` at `0x18001fa6b`
- `msvcrt!swscanf_s` at `0x18001fa6b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001fa89`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001fa89`

## string_xrefs

- `0x18001fad7`: `admin\wmi\events\forwarding\common\timehelp.cpp`

## pseudocode

```c
char __fastcall StringToSystemTime(const unsigned __int16 *a1, struct _SYSTEMTIME *a2, struct _FILETIME *a3)
{
  unsigned __int64 v3; // rax
  WORD *p_wMonth; // r9
  const wchar_t *v7; // rdx
  WORD *p_wMinute; // [rsp+30h] [rbp-29h]
  WORD *p_wSecond; // [rsp+38h] [rbp-21h]
  void **pExceptionObject; // [rsp+50h] [rbp-9h] BYREF
  char v12; // [rsp+58h] [rbp-1h]
  const char *v13; // [rsp+60h] [rbp+7h]
  __int64 v14; // [rsp+68h] [rbp+Fh]
  __int64 v15; // [rsp+70h] [rbp+17h]
  int v16; // [rsp+78h] [rbp+1Fh]
  int v17; // [rsp+7Ch] [rbp+23h]
  int v18; // [rsp+80h] [rbp+27h]
  unsigned __int64 v19; // [rsp+D8h] [rbp+7Fh] BYREF

  *a2 = 0;
  v19 = 0;
  v3 = -1;
  do
    ++v3;
  while ( a1[v3] );
  if ( v3 < 0x13 )
    return 0;
  p_wSecond = &a2->wSecond;
  p_wMonth = &a2->wMonth;
  p_wMinute = &a2->wMinute;
  v7 = L"%4hd-%2hd-%2hdT%2hd:%2hd:%2hd.%I64uZ";
  if ( a1[4] != 45 )
    v7 = L"%5hd-%2hd-%2hdT%2hd:%2hd:%2hd.%I64uZ";
  if ( swscanf_s(a1, v7, a2, p_wMonth, &a2->wDay, &a2->wHour, p_wMinute, p_wSecond, &v19) < 6 )
    return 0;
  if ( a3 )
  {
    SystemTimeToFileTime(a2, a3);
    if ( v19 >= 0x3B9ACA00 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_610b8bfd60293761ca8071fb3cb577e0_Traceguids, 13);
      }
      v12 = 0;
      v13 = "admin\\wmi\\events\\forwarding\\common\\timehelp.cpp";
      v14 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v15 = 0;
      v16 = 13;
      v17 = -1;
      v18 = 158;
      throw (wmi::GenericException *)&pExceptionObject;
    }
  }
  else
  {
    a2->wMilliseconds = v19;
  }
  return 1;
}

```

## disassembly

```asm
0x18001f9e8  push    rbp
0x18001f9ea  push    rbx
0x18001f9eb  push    rsi
0x18001f9ec  push    rdi
0x18001f9ed  lea     rbp, [rsp-3Fh]
0x18001f9f2  sub     rsp, 98h
0x18001f9f9  xor     esi, esi
0x18001f9fb  xorps   xmm0, xmm0
0x18001f9fe  movups  xmmword ptr [rdx], xmm0
0x18001fa01  mov     [rbp+57h+arg_18], rsi
0x18001fa05  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fa09  mov     rdi, r8
0x18001fa0c  mov     rbx, rdx
0x18001fa0f  inc     rax
0x18001fa12  cmp     [rcx+rax*2], si
0x18001fa16  jnz     short loc_18001FA0F
0x18001fa18  cmp     rax, 13h
0x18001fa1c  jb      loc_18001FB27
0x18001fa22  lea     rax, [rdx+0Ch]
0x18001fa26  add     rdx, 0Ah
0x18001fa2a  cmp     word ptr [rcx+8], 2Dh ; '-'
0x18001fa2f  lea     r8, [rbx+8]
0x18001fa33  lea     r11, [rbp+57h+arg_18]
0x18001fa37  mov     [rsp+0B0h+var_70], r11
0x18001fa3c  lea     r10, [rbx+6]
0x18001fa40  mov     [rsp+0B0h+var_78], rax
0x18001fa45  lea     r9, [rbx+2]
0x18001fa49  mov     [rsp+0B0h+var_80], rdx
0x18001fa4e  lea     rdx, a4hd2hd2hdt2hd2; "%4hd-%2hd-%2hdT%2hd:%2hd:%2hd.%I64uZ"
0x18001fa55  mov     [rsp+0B0h+var_88], r8
0x18001fa5a  mov     r8, rbx
0x18001fa5d  mov     [rsp+0B0h+var_90], r10
0x18001fa62  jz      short loc_18001FA6B
0x18001fa64  lea     rdx, Format; "%5hd-%2hd-%2hdT%2hd:%2hd:%2hd.%I64uZ"
0x18001fa6b  call    cs:__imp_swscanf_s
0x18001fa71  cmp     eax, 6
0x18001fa74  jl      loc_18001FB27
0x18001fa7a  test    rdi, rdi
0x18001fa7d  jz      loc_18001FB1B
0x18001fa83  mov     rdx, rdi; lpFileTime
0x18001fa86  mov     rcx, rbx; lpSystemTime
0x18001fa89  call    cs:__imp_SystemTimeToFileTime
0x18001fa8f  cmp     [rbp+57h+arg_18], 3B9ACA00h
0x18001fa97  jb      loc_18001FB23
0x18001fa9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001faa4  lea     rax, WPP_GLOBAL_Control
0x18001faab  mov     ebx, 0Dh
0x18001fab0  cmp     rcx, rax
0x18001fab3  jz      short loc_18001FAD7
0x18001fab5  test    byte ptr [rcx+1Ch], 1
0x18001fab9  jz      short loc_18001FAD7
0x18001fabb  cmp     byte ptr [rcx+19h], 2
0x18001fabf  jb      short loc_18001FAD7
0x18001fac1  mov     rcx, [rcx+10h]
0x18001fac5  lea     edx, [rbx+1]
0x18001fac8  mov     r9d, ebx
0x18001facb  lea     r8, WPP_610b8bfd60293761ca8071fb3cb577e0_Traceguids
0x18001fad2  call    WPP_SF_D
0x18001fad7  lea     rax, aAdminWmiEvents_2; "admin\\wmi\\events\\forwarding\\common"...
0x18001fade  mov     [rbp+57h+var_58], sil
0x18001fae2  mov     [rbp+57h+var_50], rax
0x18001fae6  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001faed  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001faf4  mov     [rbp+57h+var_48], rsi
0x18001faf8  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001fafc  mov     [rbp+57h+pExceptionObject], rax
0x18001fb00  mov     [rbp+57h+var_40], rsi
0x18001fb04  mov     [rbp+57h+var_38], ebx
0x18001fb07  mov     [rbp+57h+var_34], 0FFFFFFFFh
0x18001fb0e  mov     [rbp+57h+var_30], 9Eh
0x18001fb15  call    _CxxThrowException_0
0x18001fb1b  movzx   eax, word ptr [rbp+57h+arg_18]
0x18001fb1f  mov     [rbx+0Eh], ax
0x18001fb23  mov     al, 1
0x18001fb25  jmp     short loc_18001FB29
0x18001fb27  xor     al, al
0x18001fb29  add     rsp, 98h
0x18001fb30  pop     rdi
0x18001fb31  pop     rsi
0x18001fb32  pop     rbx
0x18001fb33  pop     rbp
0x18001fb34  retn
```
