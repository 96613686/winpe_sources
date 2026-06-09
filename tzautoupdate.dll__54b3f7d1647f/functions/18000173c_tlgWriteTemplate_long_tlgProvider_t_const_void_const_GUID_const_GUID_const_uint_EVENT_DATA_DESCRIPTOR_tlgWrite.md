# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x18000173c`
- end: `0x18000182f`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4@Z`
- size: `243`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dc80`
- `0x180014704`
- `0x1800169f8`

## callees

- `0x18000169c`
- `0x18000173c`
- `0x18001b150`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6,
        const unsigned __int16 **a7)
{
  __int64 v8; // rcx
  int v9; // r8d
  const unsigned __int16 *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  const unsigned __int16 *v13; // rdx
  _BYTE v15[32]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v16; // [rsp+50h] [rbp-48h]
  __int64 v17; // [rsp+58h] [rbp-40h]
  const unsigned __int16 *v18; // [rsp+60h] [rbp-38h]
  int v19; // [rsp+68h] [rbp-30h]
  int v20; // [rsp+6Ch] [rbp-2Ch]
  const unsigned __int16 *v21; // [rsp+70h] [rbp-28h]
  int v22; // [rsp+78h] [rbp-20h]
  int v23; // [rsp+7Ch] [rbp-1Ch]

  v8 = -1;
  v9 = 2;
  v10 = *a7;
  if ( *a7 )
  {
    v11 = -1;
    do
      ++v11;
    while ( v10[v11] );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = &qword_180021DC8;
    v12 = 2;
  }
  v22 = v12;
  v21 = v10;
  v23 = 0;
  v13 = *a6;
  if ( *a6 )
  {
    do
      ++v8;
    while ( v13[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v13 = &qword_180021DC8;
  }
  v16 = a5;
  v18 = v13;
  v19 = v9;
  v20 = 0;
  v17 = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180030000, a2, 0, 0, 5, v15);
}

```

## disassembly

```asm
0x18000173c  sub     rsp, 98h
0x180001743  mov     rax, cs:__security_cookie
0x18000174a  xor     rax, rsp
0x18000174d  mov     [rsp+98h+var_18], rax
0x180001755  mov     rax, [rsp+98h+arg_30]
0x18000175d  mov     r10, rdx
0x180001760  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001764  xor     r9d, r9d
0x180001767  mov     r8d, 2
0x18000176d  mov     rdx, [rax]
0x180001770  test    rdx, rdx
0x180001773  jz      short loc_18000178B
0x180001775  mov     rax, rcx
0x180001778  inc     rax
0x18000177b  cmp     [rdx+rax*2], r9w
0x180001780  jnz     short loc_180001778
0x180001782  lea     eax, ds:2[rax*2]
0x180001789  jmp     short loc_180001795
0x18000178b  lea     rdx, qword_180021DC8
0x180001792  mov     eax, r8d
0x180001795  mov     [rsp+98h+var_20], eax
0x180001799  mov     rax, [rsp+98h+arg_28]
0x1800017a1  mov     [rsp+98h+var_28], rdx
0x1800017a6  mov     [rsp+98h+var_1C], r9d
0x1800017ab  mov     rdx, [rax]
0x1800017ae  test    rdx, rdx
0x1800017b1  jz      short loc_1800017C7
0x1800017b3  inc     rcx
0x1800017b6  cmp     [rdx+rcx*2], r9w
0x1800017bb  jnz     short loc_1800017B3
0x1800017bd  lea     r8d, ds:2[rcx*2]
0x1800017c5  jmp     short loc_1800017CE
0x1800017c7  lea     rdx, qword_180021DC8
0x1800017ce  mov     rax, [rsp+98h+arg_20]
0x1800017d6  lea     rcx, dword_180030000
0x1800017dd  mov     [rsp+98h+var_48], rax
0x1800017e2  lea     rax, [rsp+98h+var_68]
0x1800017e7  mov     [rsp+98h+var_38], rdx
0x1800017ec  mov     rdx, r10
0x1800017ef  mov     [rsp+98h+var_30], r8d
0x1800017f4  xor     r8d, r8d
0x1800017f7  mov     [rsp+98h+var_70], rax
0x1800017fc  mov     [rsp+98h+var_78], 5
0x180001804  mov     [rsp+98h+var_2C], r9d
0x180001809  mov     [rsp+98h+var_40], 8
0x180001812  call    _tlgWriteTransfer_EventWriteTransfer
0x180001817  mov     rcx, [rsp+98h+var_18]
0x18000181f  xor     rcx, rsp; StackCookie
0x180001822  call    __security_check_cookie
0x180001827  add     rsp, 98h
0x18000182e  retn
```
