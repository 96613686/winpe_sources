# CSrDrvWuHelper::_GetWindirPathFromBootVolumeProp(_SPP_BOOT_VOLUME_PROP const *,CBsString *)

- ea: `0x18000c890`
- end: `0x18000ca92`
- name: `?_GetWindirPathFromBootVolumeProp@CSrDrvWuHelper@@CAJPEBU_SPP_BOOT_VOLUME_PROP@@PEAVCBsString@@@Z`
- size: `514`
- prototype: `__int64 __fastcall(const struct _SPP_BOOT_VOLUME_PROP *, struct CBsString *, __int64, unsigned __int16)`
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000a790`
- `0x18000ab80`
- `0x18000af70`
- `0x18000ca98`

## callees

- `0x180003ce0`
- `0x18000c890`
- `0x18000ceb4`
- `0x18000d348`
- `0x18000d43c`
- `0x180014f38`
- `0x180015590`
- `0x180015760`

## string_xrefs

- `0x18000c8e0`: `CSrDrvWuHelper::_GetWindirPathFromBootVolumeProp`

## pseudocode

```c
__int64 __fastcall CSrDrvWuHelper::_GetWindirPathFromBootVolumeProp(
        const struct _SPP_BOOT_VOLUME_PROP *a1,
        struct CBsString *a2,
        __int64 a3,
        unsigned __int16 a4)
{
  __int16 v6; // ax
  _WORD *v7; // rcx
  __int64 v8; // rdx
  unsigned __int64 v9; // rax
  bool v10; // cf
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // r9
  _WORD *v13; // rcx
  unsigned int v14; // ebx
  const unsigned __int16 *v16; // [rsp+20h] [rbp-79h]
  const unsigned __int16 *v17; // [rsp+28h] [rbp-71h]
  const unsigned __int16 *v18; // [rsp+30h] [rbp-69h]
  const unsigned __int16 *v19; // [rsp+38h] [rbp-61h]
  const unsigned __int16 *v20; // [rsp+40h] [rbp-59h]
  const unsigned __int16 *v21; // [rsp+48h] [rbp-51h]
  const unsigned __int16 *v22; // [rsp+50h] [rbp-49h]
  unsigned __int16 *v23; // [rsp+60h] [rbp-39h] BYREF
  __int64 v24; // [rsp+68h] [rbp-31h]
  unsigned __int16 *v25[2]; // [rsp+70h] [rbp-29h] BYREF
  _QWORD v26[2]; // [rsp+80h] [rbp-19h] BYREF
  int v27; // [rsp+90h] [rbp-9h] BYREF
  __int16 v28; // [rsp+94h] [rbp-5h]
  __int16 v29; // [rsp+96h] [rbp-3h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v27,
    "CSrDrvWuHelper::_GetWindirPathFromBootVolumeProp",
    0x3C6u,
    a4);
  v25[0] = (unsigned __int16 *)qword_18001A620;
  v26[0] = qword_18001A620;
  v23 = (unsigned __int16 *)qword_18001A620;
  v6 = 971;
  v25[1] = 0;
  v26[1] = 0;
  v24 = 0;
  if ( !a2 )
    goto LABEL_5;
  v27 = 0;
  v28 = 971;
  if ( *((_DWORD *)a2 + 2) )
  {
    v7 = *(_WORD **)a2;
    *((_DWORD *)a2 + 2) = 0;
    *v7 = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids,
      *((_QWORD *)a1 + 2));
  v8 = *((_QWORD *)a1 + 2);
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(v8 + 2 * v9) );
  v10 = v9 < 3;
  v6 = 977;
  if ( v10 )
  {
LABEL_5:
    v27 = -2147024809;
    goto LABEL_6;
  }
  v27 = 0;
  v28 = 977;
  CBsString::Append((CBsString *)v25, (const unsigned __int16 *)(v8 + 6));
  v11 = (const unsigned __int16 *)*((_QWORD *)a1 + 6);
  if ( !v11 )
    goto LABEL_25;
  v27 = CBsString::Append((CBsString *)&v23, v11);
  v6 = 982;
  if ( v27 < 0 )
  {
LABEL_6:
    v29 = v6;
    goto LABEL_28;
  }
  v28 = 982;
  if ( !(_DWORD)v24 )
  {
    v27 = -2147020579;
LABEL_20:
    v6 = 983;
    goto LABEL_6;
  }
  v27 = CBsString::_CombinePathImpl((CBsString *)&v23, v25[0], 0, v12, v16, v17, v18, v19, v20, v21, v22);
  if ( v27 < 0 )
    goto LABEL_20;
  v28 = 983;
  if ( *((_DWORD *)a2 + 2) )
  {
    v13 = *(_WORD **)a2;
    *((_DWORD *)a2 + 2) = 0;
    *v13 = 0;
  }
  v27 = CBsString::Append(a2, v23);
  v6 = 984;
  if ( v27 < 0 )
    goto LABEL_6;
  v28 = 984;
LABEL_25:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids, *(_QWORD *)a2);
LABEL_28:
  v14 = v27;
  CBsString::_Release((CBsString *)&v23);
  CBsString::_Release((CBsString *)v26);
  CBsString::_Release((CBsString *)v25);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v27);
  return v14;
}

```

## disassembly

```asm
0x18000c890  push    rbp
0x18000c892  push    rbx
0x18000c893  push    rsi
0x18000c894  push    rdi
0x18000c895  push    r14
0x18000c897  lea     rbp, [rsp-37h]
0x18000c89c  sub     rsp, 0D0h
0x18000c8a3  mov     rbx, rdx
0x18000c8a6  mov     rdi, rcx
0x18000c8a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8b0  lea     r14, WPP_GLOBAL_Control
0x18000c8b7  cmp     rcx, r14
0x18000c8ba  jz      short loc_18000C8DA
0x18000c8bc  test    dword ptr [rcx+1Ch], 20000000h
0x18000c8c3  jz      short loc_18000C8DA
0x18000c8c5  mov     rcx, [rcx+10h]
0x18000c8c9  lea     r8, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids
0x18000c8d0  mov     edx, 26h ; '&'
0x18000c8d5  call    WPP_SF_
0x18000c8da  mov     r8d, 3C6h; unsigned __int16
0x18000c8e0  lea     rdx, aCsrdrvwuhelper; "CSrDrvWuHelper::_GetWindirPathFromBootV"...
0x18000c8e7  lea     rcx, [rbp+57h+var_60]; this
0x18000c8eb  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000c8f0  lea     rax, qword_18001A620
0x18000c8f7  xor     esi, esi
0x18000c8f9  mov     [rbp+57h+var_80], rax
0x18000c8fd  mov     [rbp+57h+var_70], rax
0x18000c901  mov     [rbp+57h+var_90], rax
0x18000c905  mov     eax, 3CBh
0x18000c90a  mov     [rbp+57h+var_78], rsi
0x18000c90e  mov     [rbp+57h+var_68], rsi
0x18000c912  mov     [rbp+57h+var_88], rsi
0x18000c916  test    rbx, rbx
0x18000c919  jnz     short loc_18000C92B
0x18000c91b  mov     [rbp+57h+var_60], 80070057h
0x18000c922  mov     [rbp+57h+var_5A], ax
0x18000c926  jmp     loc_18000CA5B
0x18000c92b  mov     [rbp+57h+var_60], esi
0x18000c92e  mov     [rbp+57h+var_5C], ax
0x18000c932  cmp     [rbx+8], esi
0x18000c935  jz      short loc_18000C940
0x18000c937  mov     rcx, [rbx]
0x18000c93a  mov     [rbx+8], esi
0x18000c93d  mov     [rcx], si
0x18000c940  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c947  cmp     rcx, r14
0x18000c94a  jz      short loc_18000C96E
0x18000c94c  test    dword ptr [rcx+1Ch], 8000000h
0x18000c953  jz      short loc_18000C96E
0x18000c955  mov     r9, [rdi+10h]
0x18000c959  lea     r8, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids
0x18000c960  mov     rcx, [rcx+10h]
0x18000c964  mov     edx, 27h ; '''
0x18000c969  call    WPP_SF_S
0x18000c96e  mov     rdx, [rdi+10h]
0x18000c972  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c976  inc     rax
0x18000c979  cmp     [rdx+rax*2], si
0x18000c97d  jnz     short loc_18000C976
0x18000c97f  cmp     rax, 3
0x18000c983  mov     eax, 3D1h
0x18000c988  jb      short loc_18000C91B
0x18000c98a  mov     [rbp+57h+var_60], esi
0x18000c98d  mov     [rbp+57h+var_5C], ax
0x18000c991  add     rdx, 6; unsigned __int16 *
0x18000c995  lea     rcx, [rbp+57h+var_80]; this
0x18000c999  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18000c99e  mov     rdx, [rdi+30h]; unsigned __int16 *
0x18000c9a2  test    rdx, rdx
0x18000c9a5  jz      loc_18000CA2E
0x18000c9ab  lea     rcx, [rbp+57h+var_90]; this
0x18000c9af  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18000c9b4  mov     [rbp+57h+var_60], eax
0x18000c9b7  test    eax, eax
0x18000c9b9  mov     eax, 3D6h
0x18000c9be  js      loc_18000C922
0x18000c9c4  mov     [rbp+57h+var_5C], ax
0x18000c9c8  cmp     dword ptr [rbp+57h+var_88], esi
0x18000c9cb  jnz     short loc_18000C9D6
0x18000c9cd  mov     [rbp+57h+var_60], 800710DDh
0x18000c9d4  jmp     short loc_18000C9ED
0x18000c9d6  mov     rdx, [rbp+57h+var_80]; unsigned __int16 *
0x18000c9da  lea     rcx, [rbp+57h+var_90]; this
0x18000c9de  xor     r8d, r8d; unsigned __int16 *
0x18000c9e1  call    ?_CombinePathImpl@CBsString@@AEAAJPEBG000000000@Z; CBsString::_CombinePathImpl(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000c9e6  mov     [rbp+57h+var_60], eax
0x18000c9e9  test    eax, eax
0x18000c9eb  jns     short loc_18000C9F7
0x18000c9ed  mov     eax, 3D7h
0x18000c9f2  jmp     loc_18000C922
0x18000c9f7  mov     eax, 3D7h
0x18000c9fc  mov     [rbp+57h+var_5C], ax
0x18000ca00  cmp     [rbx+8], esi
0x18000ca03  jz      short loc_18000CA0E
0x18000ca05  mov     rcx, [rbx]
0x18000ca08  mov     [rbx+8], esi
0x18000ca0b  mov     [rcx], si
0x18000ca0e  mov     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x18000ca12  mov     rcx, rbx; this
0x18000ca15  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18000ca1a  mov     [rbp+57h+var_60], eax
0x18000ca1d  test    eax, eax
0x18000ca1f  mov     eax, 3D8h
0x18000ca24  js      loc_18000C922
0x18000ca2a  mov     [rbp+57h+var_5C], ax
0x18000ca2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca35  cmp     rcx, r14
0x18000ca38  jz      short loc_18000CA5B
0x18000ca3a  test    dword ptr [rcx+1Ch], 8000000h
0x18000ca41  jz      short loc_18000CA5B
0x18000ca43  mov     r9, [rbx]
0x18000ca46  lea     r8, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids
0x18000ca4d  mov     rcx, [rcx+10h]
0x18000ca51  mov     edx, 28h ; '('
0x18000ca56  call    WPP_SF_S
0x18000ca5b  mov     ebx, [rbp+57h+var_60]
0x18000ca5e  lea     rcx, [rbp+57h+var_90]; this
0x18000ca62  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000ca67  lea     rcx, [rbp+57h+var_70]; this
0x18000ca6b  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000ca70  lea     rcx, [rbp+57h+var_80]; this
0x18000ca74  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000ca79  lea     rcx, [rbp+57h+var_60]; this
0x18000ca7d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000ca82  mov     eax, ebx
0x18000ca84  add     rsp, 0D0h
0x18000ca8b  pop     r14
0x18000ca8d  pop     rdi
0x18000ca8e  pop     rsi
0x18000ca8f  pop     rbx
0x18000ca90  pop     rbp
0x18000ca91  retn
```
