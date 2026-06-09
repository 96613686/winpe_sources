# CWdsComMetadataEntry::get_GuidValue(ushort * *)

- ea: `0x180012090`
- end: `0x18001229c`
- name: `?get_GuidValue@CWdsComMetadataEntry@@UEAAJPEAPEAG@Z`
- size: `524`
- prototype: `__int64 __fastcall(CWdsComMetadataEntry *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800085fc`
- `0x180012090`
- `0x180014d58`
- `0x180014ee0`
- `0x180015660`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180012232`
- `OLEAUT32!__imp_SysAllocString` at `0x180012232`
- `OLEAUT32!__imp_SysFreeString` at `0x18001226c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001226c`

## string_xrefs

- `0x180012127`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`
- `0x18001217d`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`
- `0x180012218`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`
- `0x18001223e`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataEntry::get_GuidValue(CWdsComMetadataEntry *this, unsigned __int16 **a2)
{
  __int64 v2; // r15
  __int64 v5; // r14
  unsigned int v6; // ebx
  signed int v7; // edi
  const char *v8; // rdx
  const char *v9; // rdx
  unsigned __int16 *v10; // rdi
  __int128 v12; // [rsp+70h] [rbp-39h]
  OLECHAR psz[8]; // [rsp+80h] [rbp-29h] BYREF
  __int128 v14; // [rsp+90h] [rbp-19h]
  __int128 v15; // [rsp+A0h] [rbp-9h]
  __int128 v16; // [rsp+B0h] [rbp+7h]
  __int64 v17; // [rsp+C0h] [rbp+17h]
  int v18; // [rsp+C8h] [rbp+1Fh]
  wchar_t v19; // [rsp+CCh] [rbp+23h]

  LODWORD(v2) = 0;
  *(_OWORD *)psz = *(_OWORD *)L"{aed06655-9679-4b3d-bec2-68eb3234e6a7}";
  LOBYTE(v5) = 0;
  v15 = *(_OWORD *)L"b3d-bec2-68eb3234e6a7}";
  v14 = *(_OWORD *)L"5-9679-4b3d-bec2-68eb3234e6a7}";
  v18 = *(_DWORD *)L"7}";
  v17 = *(_QWORD *)L"4e6a7}";
  v12 = 0u;
  v16 = *(_OWORD *)L"-68eb3234e6a7}";
  v19 = aAed0665596794b[38];
  if ( a2
    || (v6 = -2147024809,
        (int)ElValidateHr(-2147024809, 0, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x26Au) >= 0) )
  {
    v7 = 0;
    if ( *((_DWORD *)this + 26) == 6 )
    {
      v12 = *((_OWORD *)this + 7);
      v5 = *((_QWORD *)this + 15);
      v2 = *((_QWORD *)this + 14);
    }
    else
    {
      v7 = ElValidateWin32(0xDu, (const char *)a2, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x6C3u);
    }
    if ( ElValidateWin32(v7, (const char *)a2, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x26Eu) )
    {
      v6 = (unsigned __int16)v7 | 0x80070000;
      if ( v7 <= 0 )
        return (unsigned int)v7;
    }
    else
    {
      v6 = StringCchPrintfW(
             psz,
             0x27u,
             L"{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
             (unsigned int)v2,
             WORD2(v12),
             WORD3(v12),
             (unsigned __int8)v5,
             BYTE9(v12),
             BYTE10(v12),
             BYTE11(v12),
             BYTE12(v12),
             BYTE13(v12),
             BYTE14(v12),
             HIBYTE(v12),
             v12);
      if ( (int)ElValidateHr(v6, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x274u) >= 0 )
      {
        v6 = 0;
        v10 = SysAllocString(psz);
        if ( !v10 )
          v6 = -2147024882;
        if ( (int)ElValidateHr(v6, v9, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x277u) >= 0 )
        {
          *a2 = v10;
          v10 = 0;
        }
        if ( v10 )
          SysFreeString(v10);
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180012090  mov     [rsp-8+arg_10], rbx
0x180012095  mov     [rsp-8+arg_18], rsi
0x18001209a  push    rbp
0x18001209b  push    rdi
0x18001209c  push    r12
0x18001209e  push    r14
0x1800120a0  push    r15
0x1800120a2  lea     rbp, [rsp-37h]
0x1800120a7  sub     rsp, 0E0h
0x1800120ae  mov     rax, cs:__security_cookie
0x1800120b5  xor     rax, rsp
0x1800120b8  mov     [rbp+57h+var_30], rax
0x1800120bc  movaps  xmm0, xmmword ptr cs:aAed0665596794b; "{aed06655-9679-4b3d-bec2-68eb3234e6a7}"
0x1800120c3  xor     r15d, r15d
0x1800120c6  movaps  xmm1, xmmword ptr cs:aAed0665596794b+10h; "5-9679-4b3d-bec2-68eb3234e6a7}"
0x1800120cd  mov     r12, rdx
0x1800120d0  mov     eax, dword ptr cs:aAed0665596794b+48h; "7}"
0x1800120d6  mov     rsi, rcx
0x1800120d9  movaps  xmmword ptr [rbp+57h+psz], xmm0
0x1800120dd  mov     r14d, r15d
0x1800120e0  movaps  xmm0, xmmword ptr cs:aAed0665596794b+20h; "b3d-bec2-68eb3234e6a7}"
0x1800120e7  movaps  [rbp+57h+var_60], xmm0
0x1800120eb  movsd   xmm0, qword ptr cs:aAed0665596794b+40h; "4e6a7}"
0x1800120f3  movaps  [rbp+57h+var_70], xmm1
0x1800120f7  movaps  xmm1, xmmword ptr cs:aAed0665596794b+30h; "-68eb3234e6a7}"
0x1800120fe  mov     [rbp+57h+var_38], eax
0x180012101  movzx   eax, word ptr cs:aAed0665596794b+4Ch; ""
0x180012108  movsd   [rbp+57h+var_40], xmm0
0x18001210d  mov     qword ptr [rbp+57h+var_90], r15
0x180012111  mov     qword ptr [rbp+57h+var_90+8], r15
0x180012115  movaps  [rbp+57h+var_50], xmm1
0x180012119  mov     [rbp+57h+var_34], ax
0x18001211d  test    rdx, rdx
0x180012120  jnz     short loc_180012143
0x180012122  mov     ebx, 80070057h
0x180012127  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18001212e  mov     ecx, ebx; int
0x180012130  mov     r9d, 26Ah; unsigned int
0x180012136  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18001213b  test    eax, eax
0x18001213d  js      loc_180012272
0x180012143  xor     edi, edi
0x180012145  cmp     dword ptr [rsi+68h], 6
0x180012149  jnz     short loc_18001215E
0x18001214b  movups  xmm0, xmmword ptr [rsi+70h]
0x18001214f  movdqu  [rbp+57h+var_90], xmm0
0x180012154  mov     r14, qword ptr [rbp+57h+var_90+8]
0x180012158  mov     r15, qword ptr [rbp+57h+var_90]
0x18001215c  jmp     short loc_180012177
0x18001215e  mov     r9d, 6C3h; unsigned int
0x180012164  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18001216b  mov     ecx, 0Dh; unsigned int
0x180012170  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180012175  mov     edi, eax
0x180012177  mov     r9d, 26Eh; unsigned int
0x18001217d  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180012184  mov     ecx, edi; unsigned int
0x180012186  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001218b  test    eax, eax
0x18001218d  jz      short loc_1800121A2
0x18001218f  movzx   ebx, di
0x180012192  or      ebx, 80070000h
0x180012198  test    edi, edi
0x18001219a  cmovle  ebx, edi
0x18001219d  jmp     loc_180012272
0x1800121a2  movzx   eax, byte ptr [rbp+57h+var_90+0Fh]
0x1800121a6  mov     r9d, r15d
0x1800121a9  movzx   ecx, byte ptr [rbp+57h+var_90+0Eh]
0x1800121ad  movzx   edx, byte ptr [rbp+57h+var_90+0Dh]
0x1800121b1  movzx   r8d, byte ptr [rbp+57h+var_90+0Ch]
0x1800121b6  movzx   r10d, byte ptr [rbp+57h+var_90+0Bh]
0x1800121bb  movzx   r11d, byte ptr [rbp+57h+var_90+0Ah]
0x1800121c0  movzx   ebx, byte ptr [rbp+57h+var_90+9]
0x1800121c4  movzx   esi, word ptr [rbp+57h+var_90+6]
0x1800121c8  mov     [rsp+100h+var_98], eax
0x1800121cc  mov     [rsp+100h+var_A0], ecx
0x1800121d0  lea     rcx, [rbp+57h+psz]; Buffer
0x1800121d4  mov     [rsp+100h+var_A8], edx
0x1800121d8  mov     edx, 27h ; '''; unsigned __int64
0x1800121dd  mov     [rsp+100h+var_B0], r8d
0x1800121e2  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x1800121e9  mov     [rsp+100h+var_B8], r10d
0x1800121ee  mov     [rsp+100h+var_C0], r11d
0x1800121f3  mov     [rsp+100h+var_C8], ebx
0x1800121f7  movzx   edi, r14b
0x1800121fb  movzx   r14d, word ptr [rbp+57h+var_90+4]
0x180012200  mov     [rsp+100h+var_D0], edi
0x180012204  mov     [rsp+100h+var_D8], esi
0x180012208  mov     [rsp+100h+var_E0], r14d
0x18001220d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012212  mov     r9d, 274h; unsigned int
0x180012218  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18001221f  mov     ecx, eax; int
0x180012221  mov     ebx, eax
0x180012223  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180012228  test    eax, eax
0x18001222a  js      short loc_180012272
0x18001222c  lea     rcx, [rbp+57h+psz]; psz
0x180012230  xor     ebx, ebx
0x180012232  call    cs:__imp_SysAllocString
0x180012238  mov     r9d, 277h; unsigned int
0x18001223e  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180012245  mov     rdi, rax
0x180012248  mov     eax, 8007000Eh
0x18001224d  test    rdi, rdi
0x180012250  cmovz   ebx, eax
0x180012253  mov     ecx, ebx; int
0x180012255  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18001225a  test    eax, eax
0x18001225c  js      short loc_180012264
0x18001225e  mov     [r12], rdi
0x180012262  xor     edi, edi
0x180012264  test    rdi, rdi
0x180012267  jz      short loc_180012272
0x180012269  mov     rcx, rdi; bstrString
0x18001226c  call    cs:__imp_SysFreeString
0x180012272  mov     eax, ebx
0x180012274  mov     rcx, [rbp+57h+var_30]
0x180012278  xor     rcx, rsp; StackCookie
0x18001227b  call    __security_check_cookie
0x180012280  lea     r11, [rsp+100h+var_20]
0x180012288  mov     rbx, [r11+40h]
0x18001228c  mov     rsi, [r11+48h]
0x180012290  mov     rsp, r11
0x180012293  pop     r15
0x180012295  pop     r14
0x180012297  pop     r12
0x180012299  pop     rdi
0x18001229a  pop     rbp
0x18001229b  retn
```
