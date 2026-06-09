# CommandArguments::GetOptionInteger(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,int,bool &)

- ea: `0x14000fa70`
- end: `0x14000fc3e`
- name: `?GetOptionInteger@CommandArguments@@QEBAHV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0HAEA_N@Z`
- size: `462`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400104f8`
- `0x14001c6b0`

## callees

- `0x14000fa70`
- `0x140010450`
- `0x140011904`
- `0x1400225cc`
- `0x140022cec`
- `0x140031810`

## pseudocode

```c
__int64 __fastcall CommandArguments::GetOptionInteger(
        _QWORD *a1,
        __int128 *a2,
        __int128 *a3,
        unsigned int a4,
        _BYTE *a5)
{
  __int128 v6; // xmm1
  __int64 v8; // rbx
  const wchar_t *v10; // rcx
  const wchar_t *v11; // rax
  const wchar_t *v12; // rax
  const wchar_t *Src; // rbx
  const wchar_t *v14; // rbx
  const char *v15; // [rsp+20h] [rbp-41h]
  __int128 v16; // [rsp+40h] [rbp-21h] BYREF
  __int128 v17; // [rsp+50h] [rbp-11h] BYREF
  _BYTE pExceptionObject[80]; // [rsp+60h] [rbp-1h] BYREF
  __int64 v19; // [rsp+C0h] [rbp+5Fh] BYREF

  v6 = *a2;
  v16 = *a3;
  v17 = v6;
  CommandArguments::GetOption(a1, &v19, &v17, &v16);
  v8 = v19;
  if ( v19 == *a1 )
  {
    *a5 = 0;
    return a4;
  }
  else
  {
    if ( !*(_BYTE *)(v19 + 64)
      || ((v10 = (const wchar_t *)(v19 + 72), *(_QWORD *)(v19 + 96) <= 7u)
        ? (v11 = (const wchar_t *)(v19 + 72))
        : (v11 = *(const wchar_t **)v10),
          !v11
       || (*(_QWORD *)(v19 + 96) <= 7u ? (v12 = (const wchar_t *)(v19 + 72)) : (v12 = *(const wchar_t **)v10), !*v12)) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids, 87);
      }
      v14 = (const wchar_t *)(v8 + 32);
      if ( *((_QWORD *)v14 + 3) > 7u )
        v14 = *(const wchar_t **)v14;
      EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, 0, 0, v15, 75, 9u, v14);
      throw (EvtException *)pExceptionObject;
    }
    LODWORD(v19) = 0;
    *a5 = 1;
    if ( *(_QWORD *)(v8 + 96) > 7u )
      v10 = *(const wchar_t **)v10;
    if ( swscanf(v10, L"%i", &v19) != 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids, 87);
      }
      Src = (const wchar_t *)(v8 + 32);
      if ( *((_QWORD *)Src + 3) > 7u )
        Src = *(const wchar_t **)Src;
      EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, 0, 0, v15, 84, 0x23u, Src);
      throw (EvtException *)pExceptionObject;
    }
    return (unsigned int)v19;
  }
}

```

## disassembly

```asm
0x14000fa70  push    rbp
0x14000fa72  push    rbx
0x14000fa73  push    rsi
0x14000fa74  push    rdi
0x14000fa75  lea     rbp, [rsp-37h]
0x14000fa7a  sub     rsp, 98h
0x14000fa81  movaps  xmm0, xmmword ptr [r8]
0x14000fa85  mov     esi, r9d
0x14000fa88  movaps  xmm1, xmmword ptr [rdx]
0x14000fa8b  lea     r9, [rbp+4Fh+var_70]
0x14000fa8f  lea     r8, [rbp+4Fh+var_60]
0x14000fa93  movdqa  [rbp+4Fh+var_70], xmm0
0x14000fa98  lea     rdx, [rbp+4Fh+arg_0]
0x14000fa9c  movdqa  [rbp+4Fh+var_60], xmm1
0x14000faa1  mov     rdi, rcx
0x14000faa4  call    ?GetOption@CommandArguments@@AEBA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; CommandArguments::GetOption(std::wstring_view,std::wstring_view)
0x14000faa9  mov     rbx, [rbp+4Fh+arg_0]
0x14000faad  xor     edx, edx
0x14000faaf  cmp     rbx, [rdi]
0x14000fab2  jnz     short loc_14000FAC8
0x14000fab4  mov     rax, [rbp+4Fh+arg_20]
0x14000fab8  mov     [rax], dl
0x14000faba  mov     eax, esi
0x14000fabc  add     rsp, 98h
0x14000fac3  pop     rdi
0x14000fac4  pop     rsi
0x14000fac5  pop     rbx
0x14000fac6  pop     rbp
0x14000fac7  retn
0x14000fac8  cmp     [rbx+40h], dl
0x14000facb  jz      loc_14000FBBC
0x14000fad1  lea     rcx, [rbx+48h]
0x14000fad5  cmp     qword ptr [rcx+18h], 7
0x14000fada  jbe     short loc_14000FAE1
0x14000fadc  mov     rax, [rcx]
0x14000fadf  jmp     short loc_14000FAE4
0x14000fae1  mov     rax, rcx
0x14000fae4  test    rax, rax
0x14000fae7  jz      loc_14000FBBC
0x14000faed  cmp     qword ptr [rcx+18h], 7
0x14000faf2  jbe     short loc_14000FAF9
0x14000faf4  mov     rax, [rcx]
0x14000faf7  jmp     short loc_14000FAFC
0x14000faf9  mov     rax, rcx
0x14000fafc  cmp     [rax], dx
0x14000faff  jz      loc_14000FBBC
0x14000fb05  mov     rax, [rbp+4Fh+arg_20]
0x14000fb09  mov     dword ptr [rbp+4Fh+arg_0], edx
0x14000fb0c  mov     byte ptr [rax], 1
0x14000fb0f  cmp     qword ptr [rcx+18h], 7
0x14000fb14  jbe     short loc_14000FB19
0x14000fb16  mov     rcx, [rcx]; Buffer
0x14000fb19  lea     r8, [rbp+4Fh+arg_0]
0x14000fb1d  lea     rdx, aI_1; "%i"
0x14000fb24  call    swscanf
0x14000fb29  cmp     eax, 1
0x14000fb2c  jz      loc_14000FBB4
0x14000fb32  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fb39  lea     rax, WPP_GLOBAL_Control
0x14000fb40  mov     edi, 57h ; 'W'
0x14000fb45  cmp     rcx, rax
0x14000fb48  jz      short loc_14000FB6F
0x14000fb4a  test    dword ptr [rcx+1Ch], 400000h
0x14000fb51  jz      short loc_14000FB6F
0x14000fb53  cmp     byte ptr [rcx+19h], 2
0x14000fb57  jb      short loc_14000FB6F
0x14000fb59  mov     rcx, [rcx+10h]
0x14000fb5d  lea     edx, [rdi-4Ah]
0x14000fb60  mov     r9d, edi
0x14000fb63  lea     r8, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids
0x14000fb6a  call    WPP_SF_d
0x14000fb6f  add     rbx, 20h ; ' '
0x14000fb73  cmp     qword ptr [rbx+18h], 7
0x14000fb78  jbe     short loc_14000FB7D
0x14000fb7a  mov     rbx, [rbx]
0x14000fb7d  mov     [rsp+0B0h+Src], rbx; Src
0x14000fb82  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x14000fb86  mov     [rsp+0B0h+var_80], 23h ; '#'; unsigned int
0x14000fb8e  xor     r9d, r9d; unsigned int
0x14000fb91  xor     r8d, r8d; unsigned int
0x14000fb94  mov     [rsp+0B0h+var_88], 54h ; 'T'; int
0x14000fb9c  mov     edx, edi; unsigned int
0x14000fb9e  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000fba3  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000fbaa  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x14000fbae  call    _CxxThrowException_0
0x14000fbb4  mov     eax, dword ptr [rbp+4Fh+arg_0]
0x14000fbb7  jmp     loc_14000FABC
0x14000fbbc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fbc3  lea     rax, WPP_GLOBAL_Control
0x14000fbca  mov     edi, 57h ; 'W'
0x14000fbcf  cmp     rcx, rax
0x14000fbd2  jz      short loc_14000FBF9
0x14000fbd4  test    dword ptr [rcx+1Ch], 400000h
0x14000fbdb  jz      short loc_14000FBF9
0x14000fbdd  cmp     byte ptr [rcx+19h], 2
0x14000fbe1  jb      short loc_14000FBF9
0x14000fbe3  mov     rcx, [rcx+10h]
0x14000fbe7  lea     edx, [rdi-4Bh]
0x14000fbea  mov     r9d, edi
0x14000fbed  lea     r8, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids
0x14000fbf4  call    WPP_SF_d
0x14000fbf9  add     rbx, 20h ; ' '
0x14000fbfd  cmp     qword ptr [rbx+18h], 7
0x14000fc02  jbe     short loc_14000FC07
0x14000fc04  mov     rbx, [rbx]
0x14000fc07  mov     [rsp+0B0h+Src], rbx; Src
0x14000fc0c  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x14000fc10  mov     [rsp+0B0h+var_80], 9; unsigned int
0x14000fc18  xor     r9d, r9d; unsigned int
0x14000fc1b  xor     r8d, r8d; unsigned int
0x14000fc1e  mov     [rsp+0B0h+var_88], 4Bh ; 'K'; int
0x14000fc26  mov     edx, edi; unsigned int
0x14000fc28  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000fc2d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000fc34  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x14000fc38  call    _CxxThrowException_0
```
