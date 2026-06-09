# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001118`
- end: `0x180001280`
- name: `??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `360`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e6c8`

## callees

- `0x180001118`
- `0x180005a74`
- `0x180008a90`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        const unsigned __int16 **a6,
        __int64 *a7,
        __int64 **a8,
        __int64 **a9,
        __int64 a10,
        __int64 a11)
{
  __int64 v13; // rdx
  int v14; // r8d
  __int64 *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  __int64 *v18; // rcx
  __int64 v19; // rax
  int v20; // r8d
  const unsigned __int16 *v21; // rcx
  __int64 v22; // rax
  int v23; // eax
  const unsigned __int16 *v24; // rcx
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+30h] [rbp-81h] BYREF
  const unsigned __int16 *v27; // [rsp+50h] [rbp-61h]
  int v28; // [rsp+58h] [rbp-59h]
  int v29; // [rsp+5Ch] [rbp-55h]
  const unsigned __int16 *v30; // [rsp+60h] [rbp-51h]
  int v31; // [rsp+68h] [rbp-49h]
  int v32; // [rsp+6Ch] [rbp-45h]
  __int64 v33; // [rsp+70h] [rbp-41h]
  __int64 v34; // [rsp+78h] [rbp-39h]
  __int64 *v35; // [rsp+80h] [rbp-31h]
  int v36; // [rsp+88h] [rbp-29h]
  int v37; // [rsp+8Ch] [rbp-25h]
  __int64 *v38; // [rsp+90h] [rbp-21h]
  int v39; // [rsp+98h] [rbp-19h]
  int v40; // [rsp+9Ch] [rbp-15h]
  __int64 v41; // [rsp+A0h] [rbp-11h]
  __int64 v42; // [rsp+A8h] [rbp-9h]
  __int64 v43; // [rsp+B0h] [rbp-1h]
  __int64 v44; // [rsp+B8h] [rbp+7h]

  v43 = a11;
  v41 = a10;
  v13 = -1;
  v14 = 2;
  v44 = 8;
  v42 = 4;
  v15 = *a9;
  if ( *a9 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v15 + v16) );
    v17 = 2 * v16 + 2;
  }
  else
  {
    v15 = &qword_180022030;
    v17 = 2;
  }
  v39 = v17;
  v38 = v15;
  v40 = 0;
  v18 = *a8;
  if ( *a8 )
  {
    v19 = -1;
    do
      ++v19;
    while ( *((_WORD *)v18 + v19) );
    v14 = 2 * v19 + 2;
  }
  else
  {
    v18 = &qword_180022030;
  }
  v35 = v18;
  v36 = v14;
  v20 = 1;
  v37 = 0;
  v33 = *a7;
  v34 = 16;
  v21 = *a6;
  if ( *a6 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *((_BYTE *)v21 + v22) );
    v23 = v22 + 1;
  }
  else
  {
    v21 = &dword_18002202C;
    v23 = 1;
  }
  v31 = v23;
  v30 = v21;
  v32 = 0;
  v24 = *a5;
  if ( *a5 )
  {
    do
      ++v13;
    while ( *((_BYTE *)v24 + v13) );
    v20 = v13 + 1;
  }
  else
  {
    v24 = &dword_18002202C;
  }
  v27 = v24;
  v28 = v20;
  v29 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 9u, &v26);
}

```

## disassembly

```asm
0x180001118  push    rbp
0x18000111a  lea     rbp, [rsp-1Fh]
0x18000111f  sub     rsp, 0D0h
0x180001126  mov     rax, cs:__security_cookie
0x18000112d  xor     rax, rsp
0x180001130  mov     [rbp+1Fh+var_10], rax
0x180001134  mov     rax, [rbp+1Fh+arg_50]
0x180001138  xor     r9d, r9d; int
0x18000113b  mov     [rbp+1Fh+var_20], rax
0x18000113f  mov     r11, rdx
0x180001142  mov     rax, [rbp+1Fh+arg_48]
0x180001146  mov     r10, rcx
0x180001149  mov     [rbp+1Fh+var_30], rax
0x18000114d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001151  mov     rax, [rbp+1Fh+arg_40]
0x180001155  lea     r8d, [r9+2]
0x180001159  mov     [rbp+1Fh+var_18], 8
0x180001161  mov     [rbp+1Fh+var_28], 4
0x180001169  mov     rcx, [rax]
0x18000116c  test    rcx, rcx
0x18000116f  jz      short loc_180001187
0x180001171  mov     rax, rdx
0x180001174  inc     rax
0x180001177  cmp     [rcx+rax*2], r9w
0x18000117c  jnz     short loc_180001174
0x18000117e  lea     eax, ds:2[rax*2]
0x180001185  jmp     short loc_180001191
0x180001187  lea     rcx, qword_180022030
0x18000118e  mov     eax, r8d
0x180001191  mov     [rbp+1Fh+var_38], eax
0x180001194  mov     rax, [rbp+1Fh+arg_38]
0x180001198  mov     [rbp+1Fh+var_40], rcx
0x18000119c  mov     [rbp+1Fh+var_34], r9d
0x1800011a0  mov     rcx, [rax]
0x1800011a3  test    rcx, rcx
0x1800011a6  jz      short loc_1800011BF
0x1800011a8  mov     rax, rdx
0x1800011ab  inc     rax
0x1800011ae  cmp     [rcx+rax*2], r9w
0x1800011b3  jnz     short loc_1800011AB
0x1800011b5  lea     r8d, ds:2[rax*2]
0x1800011bd  jmp     short loc_1800011C6
0x1800011bf  lea     rcx, qword_180022030
0x1800011c6  mov     rax, [rbp+1Fh+arg_30]
0x1800011ca  mov     [rbp+1Fh+var_50], rcx
0x1800011ce  mov     [rbp+1Fh+var_48], r8d
0x1800011d2  mov     r8d, 1
0x1800011d8  mov     [rbp+1Fh+var_44], r9d
0x1800011dc  mov     rcx, [rax]
0x1800011df  mov     rax, [rbp+1Fh+arg_28]
0x1800011e3  mov     [rbp+1Fh+var_60], rcx
0x1800011e7  mov     [rbp+1Fh+var_58], 10h
0x1800011ef  mov     rcx, [rax]
0x1800011f2  test    rcx, rcx
0x1800011f5  jz      short loc_180001207
0x1800011f7  mov     rax, rdx
0x1800011fa  inc     rax
0x1800011fd  cmp     [rcx+rax], r9b
0x180001201  jnz     short loc_1800011FA
0x180001203  inc     eax
0x180001205  jmp     short loc_180001211
0x180001207  lea     rcx, dword_18002202C
0x18000120e  mov     eax, r8d
0x180001211  mov     [rbp+1Fh+var_68], eax
0x180001214  mov     rax, [rbp+1Fh+arg_20]
0x180001218  mov     [rbp+1Fh+var_70], rcx
0x18000121c  mov     [rbp+1Fh+var_64], r9d
0x180001220  mov     rcx, [rax]
0x180001223  test    rcx, rcx
0x180001226  jz      short loc_180001237
0x180001228  inc     rdx
0x18000122b  cmp     [rcx+rdx], r9b
0x18000122f  jnz     short loc_180001228
0x180001231  lea     r8d, [rdx+1]
0x180001235  jmp     short loc_18000123E
0x180001237  lea     rcx, dword_18002202C
0x18000123e  lea     rax, [rsp+0D0h+var_A0]
0x180001243  mov     [rbp+1Fh+var_80], rcx
0x180001247  mov     [rbp+1Fh+var_78], r8d
0x18000124b  mov     rdx, r11; int
0x18000124e  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x180001253  xor     r8d, r8d; int
0x180001256  mov     rcx, r10; int
0x180001259  mov     [rsp+0D0h+var_B0], 9; ULONG
0x180001261  mov     [rbp+1Fh+var_74], r9d
0x180001265  call    _tlgWriteTransfer_EventWriteTransfer
0x18000126a  mov     rcx, [rbp+1Fh+var_10]
0x18000126e  xor     rcx, rsp; StackCookie
0x180001271  call    __security_check_cookie
0x180001276  add     rsp, 0D0h
0x18000127d  pop     rbp
0x18000127e  retn
```
