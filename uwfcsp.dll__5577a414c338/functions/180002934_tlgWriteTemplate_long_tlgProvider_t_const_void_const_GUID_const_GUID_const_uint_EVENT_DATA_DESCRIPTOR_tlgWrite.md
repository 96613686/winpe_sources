# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180002934`
- end: `0x180002a1f`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4444AEBU?$_tlgWrapSz@G@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, int **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c5b4`
- `0x18000c8d8`

## callees

- `0x180001ecc`
- `0x180002934`
- `0x18001a210`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        int **a11)
{
  int *v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  _BYTE v16[32]; // [rsp+30h] [rbp-81h] BYREF
  __int64 v17; // [rsp+50h] [rbp-61h]
  __int64 v18; // [rsp+58h] [rbp-59h]
  __int64 v19; // [rsp+60h] [rbp-51h]
  __int64 v20; // [rsp+68h] [rbp-49h]
  __int64 v21; // [rsp+70h] [rbp-41h]
  __int64 v22; // [rsp+78h] [rbp-39h]
  __int64 v23; // [rsp+80h] [rbp-31h]
  __int64 v24; // [rsp+88h] [rbp-29h]
  __int64 v25; // [rsp+90h] [rbp-21h]
  __int64 v26; // [rsp+98h] [rbp-19h]
  __int64 v27; // [rsp+A0h] [rbp-11h]
  __int64 v28; // [rsp+A8h] [rbp-9h]
  int *v29; // [rsp+B0h] [rbp-1h]
  int v30; // [rsp+B8h] [rbp+7h]
  int v31; // [rsp+BCh] [rbp+Bh]

  v12 = *a11;
  if ( *a11 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)v12 + v13) );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v12 = &dword_18001F7A4;
    v14 = 2;
  }
  v30 = v14;
  v27 = a10;
  v25 = a9;
  v23 = a8;
  v21 = a7;
  v19 = a6;
  v17 = a5;
  v29 = v12;
  v31 = 0;
  v28 = 4;
  v26 = 4;
  v24 = 4;
  v22 = 4;
  v20 = 4;
  v18 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 9, v16);
}

```

## disassembly

```asm
0x180002934  push    rbp
0x180002936  lea     rbp, [rsp-1Fh]
0x18000293b  sub     rsp, 0D0h
0x180002942  mov     rax, cs:__security_cookie
0x180002949  xor     rax, rsp
0x18000294c  mov     [rbp+1Fh+var_10], rax
0x180002950  mov     rax, [rbp+1Fh+arg_50]
0x180002954  mov     r10, rcx
0x180002957  xor     r9d, r9d
0x18000295a  mov     rcx, [rax]
0x18000295d  test    rcx, rcx
0x180002960  jz      short loc_180002979
0x180002962  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002966  inc     rax
0x180002969  cmp     [rcx+rax*2], r9w
0x18000296e  jnz     short loc_180002966
0x180002970  lea     eax, ds:2[rax*2]
0x180002977  jmp     short loc_180002985
0x180002979  lea     rcx, dword_18001F7A4
0x180002980  mov     eax, 2
0x180002985  mov     [rbp+1Fh+var_18], eax
0x180002988  mov     rax, [rbp+1Fh+arg_48]
0x18000298c  mov     [rbp+1Fh+var_30], rax
0x180002990  mov     rax, [rbp+1Fh+arg_40]
0x180002994  mov     [rbp+1Fh+var_40], rax
0x180002998  mov     rax, [rbp+1Fh+arg_38]
0x18000299c  mov     [rbp+1Fh+var_50], rax
0x1800029a0  mov     rax, [rbp+1Fh+arg_30]
0x1800029a4  mov     [rbp+1Fh+var_60], rax
0x1800029a8  mov     rax, [rbp+1Fh+arg_28]
0x1800029ac  mov     [rbp+1Fh+var_70], rax
0x1800029b0  mov     rax, [rbp+1Fh+arg_20]
0x1800029b4  mov     [rbp+1Fh+var_80], rax
0x1800029b8  lea     rax, [rsp+0D0h+var_A0]
0x1800029bd  mov     [rbp+1Fh+var_20], rcx
0x1800029c1  mov     rcx, r10
0x1800029c4  mov     [rsp+0D0h+var_A8], rax
0x1800029c9  mov     [rsp+0D0h+var_B0], 9
0x1800029d1  mov     [rbp+1Fh+var_14], r9d
0x1800029d5  mov     [rbp+1Fh+var_28], 4
0x1800029dd  mov     [rbp+1Fh+var_38], 4
0x1800029e5  mov     [rbp+1Fh+var_48], 4
0x1800029ed  mov     [rbp+1Fh+var_58], 4
0x1800029f5  mov     [rbp+1Fh+var_68], 4
0x1800029fd  mov     [rbp+1Fh+var_78], 8
0x180002a05  call    _tlgWriteTransfer_EventWriteTransfer
0x180002a0a  mov     rcx, [rbp+1Fh+var_10]
0x180002a0e  xor     rcx, rsp; StackCookie
0x180002a11  call    __security_check_cookie
0x180002a16  add     rsp, 0D0h
0x180002a1d  pop     rbp
0x180002a1e  retn
```
