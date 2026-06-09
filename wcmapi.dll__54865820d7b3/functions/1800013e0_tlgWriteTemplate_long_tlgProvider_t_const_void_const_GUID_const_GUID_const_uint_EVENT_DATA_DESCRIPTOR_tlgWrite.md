# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800013e0`
- end: `0x18000150f`
- name: `??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `303`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e7c8`

## callees

- `0x1800013e0`
- `0x180005a74`
- `0x180008a90`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        const unsigned __int16 **a6,
        __int64 *a7,
        __int64 **a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v12; // rdx
  __int64 *v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  int v16; // r8d
  const unsigned __int16 *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  const unsigned __int16 *v20; // rcx
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+30h] [rbp-69h] BYREF
  const unsigned __int16 *v23; // [rsp+50h] [rbp-49h]
  int v24; // [rsp+58h] [rbp-41h]
  int v25; // [rsp+5Ch] [rbp-3Dh]
  const unsigned __int16 *v26; // [rsp+60h] [rbp-39h]
  int v27; // [rsp+68h] [rbp-31h]
  int v28; // [rsp+6Ch] [rbp-2Dh]
  __int64 v29; // [rsp+70h] [rbp-29h]
  __int64 v30; // [rsp+78h] [rbp-21h]
  __int64 *v31; // [rsp+80h] [rbp-19h]
  int v32; // [rsp+88h] [rbp-11h]
  int v33; // [rsp+8Ch] [rbp-Dh]
  __int64 v34; // [rsp+90h] [rbp-9h]
  __int64 v35; // [rsp+98h] [rbp-1h]
  __int64 v36; // [rsp+A0h] [rbp+7h]
  __int64 v37; // [rsp+A8h] [rbp+Fh]

  v36 = a10;
  v34 = a9;
  v12 = -1;
  v37 = 8;
  v35 = 4;
  v13 = *a8;
  if ( *a8 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)v13 + v14) );
    v15 = 2 * v14 + 2;
  }
  else
  {
    v13 = &qword_180022030;
    v15 = 2;
  }
  v32 = v15;
  v16 = 1;
  v31 = v13;
  v33 = 0;
  v30 = 16;
  v29 = *a7;
  v17 = *a6;
  if ( *a6 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *((_BYTE *)v17 + v18) );
    v19 = v18 + 1;
  }
  else
  {
    v17 = &dword_18002202C;
    v19 = 1;
  }
  v27 = v19;
  v26 = v17;
  v28 = 0;
  v20 = *a5;
  if ( *a5 )
  {
    do
      ++v12;
    while ( *((_BYTE *)v20 + v12) );
    v16 = v12 + 1;
  }
  else
  {
    v20 = &dword_18002202C;
  }
  v23 = v20;
  v24 = v16;
  v25 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 8u, &v22);
}

```

## disassembly

```asm
0x1800013e0  push    rbp
0x1800013e2  lea     rbp, [rsp-27h]
0x1800013e7  sub     rsp, 0C0h
0x1800013ee  mov     rax, cs:__security_cookie
0x1800013f5  xor     rax, rsp
0x1800013f8  mov     [rbp+27h+var_10], rax
0x1800013fc  mov     rax, [rbp+27h+arg_48]
0x180001400  mov     r11, rdx
0x180001403  mov     [rbp+27h+var_20], rax
0x180001407  mov     r10, rcx
0x18000140a  mov     rax, [rbp+27h+arg_40]
0x18000140e  xor     r9d, r9d; int
0x180001411  mov     [rbp+27h+var_30], rax
0x180001415  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001419  mov     rax, [rbp+27h+arg_38]
0x18000141d  mov     [rbp+27h+var_18], 8
0x180001425  mov     [rbp+27h+var_28], 4
0x18000142d  mov     rcx, [rax]
0x180001430  test    rcx, rcx
0x180001433  jz      short loc_18000144B
0x180001435  mov     rax, rdx
0x180001438  inc     rax
0x18000143b  cmp     [rcx+rax*2], r9w
0x180001440  jnz     short loc_180001438
0x180001442  lea     eax, ds:2[rax*2]
0x180001449  jmp     short loc_180001457
0x18000144b  lea     rcx, qword_180022030
0x180001452  mov     eax, 2
0x180001457  mov     [rbp+27h+var_38], eax
0x18000145a  mov     r8d, 1
0x180001460  mov     rax, [rbp+27h+arg_30]
0x180001464  mov     [rbp+27h+var_40], rcx
0x180001468  mov     [rbp+27h+var_34], r9d
0x18000146c  mov     [rbp+27h+var_48], 10h
0x180001474  mov     rcx, [rax]
0x180001477  mov     rax, [rbp+27h+arg_28]
0x18000147b  mov     [rbp+27h+var_50], rcx
0x18000147f  mov     rcx, [rax]
0x180001482  test    rcx, rcx
0x180001485  jz      short loc_180001497
0x180001487  mov     rax, rdx
0x18000148a  inc     rax
0x18000148d  cmp     [rcx+rax], r9b
0x180001491  jnz     short loc_18000148A
0x180001493  inc     eax
0x180001495  jmp     short loc_1800014A1
0x180001497  lea     rcx, dword_18002202C
0x18000149e  mov     eax, r8d
0x1800014a1  mov     [rbp+27h+var_58], eax
0x1800014a4  mov     rax, [rbp+27h+arg_20]
0x1800014a8  mov     [rbp+27h+var_60], rcx
0x1800014ac  mov     [rbp+27h+var_54], r9d
0x1800014b0  mov     rcx, [rax]
0x1800014b3  test    rcx, rcx
0x1800014b6  jz      short loc_1800014C7
0x1800014b8  inc     rdx
0x1800014bb  cmp     [rcx+rdx], r9b
0x1800014bf  jnz     short loc_1800014B8
0x1800014c1  lea     r8d, [rdx+1]
0x1800014c5  jmp     short loc_1800014CE
0x1800014c7  lea     rcx, dword_18002202C
0x1800014ce  lea     rax, [rbp+27h+var_90]
0x1800014d2  mov     [rbp+27h+var_70], rcx
0x1800014d6  mov     [rbp+27h+var_68], r8d
0x1800014da  mov     rdx, r11; int
0x1800014dd  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x1800014e2  xor     r8d, r8d; int
0x1800014e5  mov     rcx, r10; int
0x1800014e8  mov     [rsp+0C0h+var_A0], 8; ULONG
0x1800014f0  mov     [rbp+27h+var_64], r9d
0x1800014f4  call    _tlgWriteTransfer_EventWriteTransfer
0x1800014f9  mov     rcx, [rbp+27h+var_10]
0x1800014fd  xor     rcx, rsp; StackCookie
0x180001500  call    __security_check_cookie
0x180001505  add     rsp, 0C0h
0x18000150c  pop     rbp
0x18000150d  retn
```
