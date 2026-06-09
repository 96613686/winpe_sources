# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &)

- ea: `0x180001010`
- end: `0x1800011c7`
- name: `??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@44AEBU?$_tlgWrapSz@G@@3@Z`
- size: `439`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, const unsigned __int16 **, __int64, __int64, __int64, __int64 **, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ac1c`

## callees

- `0x180001010`
- `0x1800011d0`
- `0x180001dc0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        const unsigned __int16 **a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 **a10,
        const unsigned __int16 **a11)
{
  __int64 v11; // rcx
  const unsigned __int16 *v12; // rax
  __int64 v13; // r8
  int v14; // r8d
  int v15; // r9d
  __int64 *v16; // r8
  __int64 v17; // rax
  bool v18; // zf
  int v19; // eax
  const unsigned __int16 *v20; // r8
  __int64 v21; // rax
  int v22; // eax
  const unsigned __int16 *v23; // r8
  _BYTE v25[32]; // [rsp+30h] [rbp-A8h] BYREF
  const unsigned __int16 *v26; // [rsp+50h] [rbp-88h]
  int v27; // [rsp+58h] [rbp-80h]
  int v28; // [rsp+5Ch] [rbp-7Ch]
  const unsigned __int16 *v29; // [rsp+60h] [rbp-78h]
  int v30; // [rsp+68h] [rbp-70h]
  int v31; // [rsp+6Ch] [rbp-6Ch]
  __int64 v32; // [rsp+70h] [rbp-68h]
  __int64 v33; // [rsp+78h] [rbp-60h]
  __int64 v34; // [rsp+80h] [rbp-58h]
  __int64 v35; // [rsp+88h] [rbp-50h]
  __int64 v36; // [rsp+90h] [rbp-48h]
  __int64 v37; // [rsp+98h] [rbp-40h]
  __int64 *v38; // [rsp+A0h] [rbp-38h]
  int v39; // [rsp+A8h] [rbp-30h]
  int v40; // [rsp+ACh] [rbp-2Ch]
  const unsigned __int16 *v41; // [rsp+B0h] [rbp-28h]
  int v42; // [rsp+B8h] [rbp-20h]
  int v43; // [rsp+BCh] [rbp-1Ch]

  v11 = -1;
  v12 = *a11;
  if ( *a11 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_BYTE *)v12 + v13) );
    v14 = v13 + 1;
    v15 = 1;
  }
  else
  {
    v15 = 1;
    v12 = &word_18000EB82;
    v14 = 1;
  }
  v41 = v12;
  v42 = v14;
  v43 = 0;
  v16 = *a10;
  if ( *a10 )
  {
    v17 = -1;
    do
      v18 = *((_WORD *)v16 + ++v17) == 0;
    while ( !v18 );
    v19 = 2 * v17 + 2;
  }
  else
  {
    v16 = &qword_18000F0B8;
    v19 = 2;
  }
  v39 = v19;
  v36 = a9;
  v34 = a8;
  v32 = a7;
  v38 = v16;
  v40 = 0;
  v37 = 4;
  v20 = *a6;
  v35 = 4;
  v33 = 4;
  if ( v20 )
  {
    v21 = -1;
    do
      ++v21;
    while ( *((_BYTE *)v20 + v21) );
    v22 = v21 + 1;
  }
  else
  {
    v20 = &word_18000EB82;
    v22 = 1;
  }
  v30 = v22;
  v29 = v20;
  v31 = 0;
  v23 = *a5;
  if ( *a5 )
  {
    do
      v18 = *((_BYTE *)v23 + ++v11) == 0;
    while ( !v18 );
    v15 = v11 + 1;
  }
  else
  {
    v23 = &word_18000EB82;
  }
  v26 = v23;
  v27 = v15;
  v28 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180013000, a2, 0, 0, 9, v25);
}

```

## disassembly

```asm
0x180001010  sub     rsp, 0D8h
0x180001017  mov     rax, cs:__security_cookie
0x18000101e  xor     rax, rsp
0x180001021  mov     [rsp+0D8h+var_18], rax
0x180001029  mov     rax, [rsp+0D8h+arg_50]
0x180001031  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180001038  mov     rax, [rax]
0x18000103b  test    rax, rax
0x18000103e  jz      short loc_180001058
0x180001040  mov     r8, rcx
0x180001043  inc     r8
0x180001046  cmp     byte ptr [rax+r8], 0
0x18000104b  jnz     short loc_180001043
0x18000104d  inc     r8d
0x180001050  mov     r9d, 1
0x180001056  jmp     short loc_180001068
0x180001058  mov     r9d, 1
0x18000105e  lea     rax, word_18000EB82
0x180001065  mov     r8d, r9d
0x180001068  xor     r10d, r10d
0x18000106b  mov     [rsp+0D8h+var_28], rax
0x180001073  mov     rax, [rsp+0D8h+arg_48]
0x18000107b  mov     [rsp+0D8h+var_20], r8d
0x180001083  mov     [rsp+0D8h+var_1C], r10d
0x18000108b  mov     r8, [rax]
0x18000108e  test    r8, r8
0x180001091  jz      short loc_1800010AB
0x180001093  mov     rax, rcx
0x180001096  cmp     [r8+rax*2+2], r10w
0x18000109c  lea     rax, [rax+1]
0x1800010a0  jnz     short loc_180001096
0x1800010a2  lea     eax, ds:2[rax*2]
0x1800010a9  jmp     short loc_1800010B7
0x1800010ab  lea     r8, qword_18000F0B8
0x1800010b2  mov     eax, 2
0x1800010b7  mov     [rsp+0D8h+var_30], eax
0x1800010be  mov     rax, [rsp+0D8h+arg_40]
0x1800010c6  mov     [rsp+0D8h+var_48], rax
0x1800010ce  mov     rax, [rsp+0D8h+arg_38]
0x1800010d6  mov     [rsp+0D8h+var_58], rax
0x1800010de  mov     rax, [rsp+0D8h+arg_30]
0x1800010e6  mov     [rsp+0D8h+var_68], rax
0x1800010eb  mov     rax, [rsp+0D8h+arg_28]
0x1800010f3  mov     [rsp+0D8h+var_38], r8
0x1800010fb  mov     [rsp+0D8h+var_2C], r10d
0x180001103  mov     [rsp+0D8h+var_40], 4
0x18000110f  mov     r8, [rax]
0x180001112  mov     [rsp+0D8h+var_50], 4
0x18000111e  mov     [rsp+0D8h+var_60], 4
0x180001127  test    r8, r8
0x18000112a  jz      short loc_18000113C
0x18000112c  mov     rax, rcx
0x18000112f  inc     rax
0x180001132  cmp     [r8+rax], r10b
0x180001136  jnz     short loc_18000112F
0x180001138  inc     eax
0x18000113a  jmp     short loc_180001146
0x18000113c  lea     r8, word_18000EB82
0x180001143  mov     eax, r9d
0x180001146  mov     [rsp+0D8h+var_70], eax
0x18000114a  mov     rax, [rsp+0D8h+arg_20]
0x180001152  mov     [rsp+0D8h+var_78], r8
0x180001157  mov     [rsp+0D8h+var_6C], r10d
0x18000115c  mov     r8, [rax]
0x18000115f  test    r8, r8
0x180001162  jz      short loc_180001175
0x180001164  cmp     [r8+rcx+1], r10b
0x180001169  lea     rcx, [rcx+1]
0x18000116d  jnz     short loc_180001164
0x18000116f  lea     r9d, [rcx+1]
0x180001173  jmp     short loc_18000117C
0x180001175  lea     r8, word_18000EB82
0x18000117c  lea     rax, [rsp+0D8h+var_A8]
0x180001181  mov     [rsp+0D8h+var_88], r8
0x180001186  mov     [rsp+0D8h+var_80], r9d
0x18000118b  lea     rcx, dword_180013000
0x180001192  mov     [rsp+0D8h+var_B0], rax
0x180001197  xor     r9d, r9d
0x18000119a  xor     r8d, r8d
0x18000119d  mov     [rsp+0D8h+var_B8], 9
0x1800011a5  mov     [rsp+0D8h+var_7C], r10d
0x1800011aa  call    _tlgWriteTransfer_EventWriteTransfer
0x1800011af  mov     rcx, [rsp+0D8h+var_18]
0x1800011b7  xor     rcx, rsp; StackCookie
0x1800011ba  call    __security_check_cookie
0x1800011bf  add     rsp, 0D8h
0x1800011c6  retn
```
