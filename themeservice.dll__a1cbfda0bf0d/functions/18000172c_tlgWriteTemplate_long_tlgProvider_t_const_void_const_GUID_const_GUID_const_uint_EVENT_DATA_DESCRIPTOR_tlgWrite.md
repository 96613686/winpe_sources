# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x18000172c`
- end: `0x180001a1b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `751`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e908`

## callees

- `0x18000172c`
- `0x180001ba8`
- `0x18000fa00`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        __int64 a8,
        _QWORD *a9,
        __int64 a10,
        _QWORD *a11,
        __int64 a12,
        _QWORD *a13,
        __int64 a14,
        _QWORD *a15,
        _QWORD *a16,
        __int64 a17,
        _QWORD *a18,
        _QWORD *a19,
        __int64 a20,
        __int64 a21,
        _QWORD *a22)
{
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax

  v23 = -1;
  if ( *a22 )
  {
    v24 = -1;
    do
      ++v24;
    while ( *(_BYTE *)(*a22 + v24) );
  }
  if ( *a19 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_WORD *)(*a19 + 2 * v25) );
  }
  if ( *a18 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_BYTE *)(*a18 + v26) );
  }
  if ( *a16 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *(_WORD *)(*a16 + 2 * v27) );
  }
  if ( *a15 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *(_BYTE *)(*a15 + v28) );
  }
  if ( *a13 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *(_BYTE *)(*a13 + v29) );
  }
  if ( *a11 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *(_WORD *)(*a11 + 2 * v30) );
  }
  if ( *a9 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *(_BYTE *)(*a9 + v31) );
  }
  if ( *a7 )
  {
    do
      ++v23;
    while ( *(_BYTE *)(*a7 + v23) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x18000172c  mov     [rsp-8+arg_10], rbx
0x180001731  push    rbp
0x180001732  push    rdi
0x180001733  push    r14
0x180001735  lea     rbp, [rsp-80h]
0x18000173a  sub     rsp, 180h
0x180001741  mov     rax, cs:__security_cookie
0x180001748  xor     rax, rsp
0x18000174b  mov     [rbp+90h+var_20], rax
0x18000174f  mov     rax, [rbp+90h+arg_A8]
0x180001756  lea     rdi, byte_180011FBB
0x18000175d  mov     r11, rdx
0x180001760  mov     r10, rcx
0x180001763  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001767  xor     ebx, ebx
0x180001769  mov     r8d, 1
0x18000176f  mov     rcx, [rax]
0x180001772  test    rcx, rcx
0x180001775  jz      short loc_180001786
0x180001777  mov     rax, rdx
0x18000177a  inc     rax
0x18000177d  cmp     [rcx+rax], bl
0x180001780  jnz     short loc_18000177A
0x180001782  inc     eax
0x180001784  jmp     short loc_18000178C
0x180001786  mov     rcx, rdi
0x180001789  mov     eax, r8d
0x18000178c  mov     [rbp+90h+var_28], eax
0x18000178f  mov     r9d, 2
0x180001795  mov     rax, [rbp+90h+arg_A0]
0x18000179c  mov     [rbp+90h+var_40], rax
0x1800017a0  mov     rax, [rbp+90h+arg_98]
0x1800017a7  mov     [rbp+90h+var_50], rax
0x1800017ab  mov     rax, [rbp+90h+arg_90]
0x1800017b2  mov     [rbp+90h+var_30], rcx
0x1800017b6  mov     [rbp+90h+var_24], ebx
0x1800017b9  mov     [rbp+90h+var_38], 4
0x1800017c1  mov     rcx, [rax]
0x1800017c4  mov     [rbp+90h+var_48], 4
0x1800017cc  test    rcx, rcx
0x1800017cf  jz      short loc_1800017E6
0x1800017d1  mov     rax, rdx
0x1800017d4  inc     rax
0x1800017d7  cmp     [rcx+rax*2], bx
0x1800017db  jnz     short loc_1800017D4
0x1800017dd  lea     eax, ds:2[rax*2]
0x1800017e4  jmp     short loc_1800017F0
0x1800017e6  lea     rcx, qword_1800125E0
0x1800017ed  mov     eax, r9d
0x1800017f0  mov     [rbp+90h+var_58], eax
0x1800017f3  mov     rax, [rbp+90h+arg_88]
0x1800017fa  mov     [rbp+90h+var_60], rcx
0x1800017fe  mov     [rbp+90h+var_54], ebx
0x180001801  mov     rcx, [rax]
0x180001804  test    rcx, rcx
0x180001807  jz      short loc_180001818
0x180001809  mov     rax, rdx
0x18000180c  inc     rax
0x18000180f  cmp     [rcx+rax], bl
0x180001812  jnz     short loc_18000180C
0x180001814  inc     eax
0x180001816  jmp     short loc_18000181E
0x180001818  mov     rcx, rdi
0x18000181b  mov     eax, r8d
0x18000181e  mov     [rbp+90h+var_68], eax
0x180001821  mov     rax, [rbp+90h+arg_80]
0x180001828  mov     [rbp+90h+var_80], rax
0x18000182c  mov     rax, [rbp+90h+arg_78]
0x180001833  mov     [rbp+90h+var_70], rcx
0x180001837  mov     [rbp+90h+var_64], ebx
0x18000183a  mov     [rbp+90h+var_78], 4
0x180001842  mov     rcx, [rax]
0x180001845  test    rcx, rcx
0x180001848  jz      short loc_18000185F
0x18000184a  mov     rax, rdx
0x18000184d  inc     rax
0x180001850  cmp     [rcx+rax*2], bx
0x180001854  jnz     short loc_18000184D
0x180001856  lea     eax, ds:2[rax*2]
0x18000185d  jmp     short loc_180001869
0x18000185f  lea     rcx, qword_1800125E0
0x180001866  mov     eax, r9d
0x180001869  mov     [rbp+90h+var_88], eax
0x18000186c  mov     rax, [rbp+90h+arg_70]
0x180001873  mov     [rbp+90h+var_90], rcx
0x180001877  mov     [rbp+90h+var_84], ebx
0x18000187a  mov     rcx, [rax]
0x18000187d  test    rcx, rcx
0x180001880  jz      short loc_180001891
0x180001882  mov     rax, rdx
0x180001885  inc     rax
0x180001888  cmp     [rcx+rax], bl
0x18000188b  jnz     short loc_180001885
0x18000188d  inc     eax
0x18000188f  jmp     short loc_180001897
0x180001891  mov     rcx, rdi
0x180001894  mov     eax, r8d
0x180001897  mov     [rbp+90h+var_98], eax
0x18000189a  mov     rax, [rbp+90h+arg_68]
0x1800018a1  mov     [rbp+90h+var_B0], rax
0x1800018a5  mov     rax, [rbp+90h+arg_60]
0x1800018ac  mov     [rbp+90h+var_A0], rcx
0x1800018b0  mov     [rbp+90h+var_94], ebx
0x1800018b3  mov     [rbp+90h+var_A8], 4
0x1800018bb  mov     rcx, [rax]
0x1800018be  test    rcx, rcx
0x1800018c1  jz      short loc_1800018D2
0x1800018c3  mov     rax, rdx
0x1800018c6  inc     rax
0x1800018c9  cmp     [rcx+rax], bl
0x1800018cc  jnz     short loc_1800018C6
0x1800018ce  inc     eax
0x1800018d0  jmp     short loc_1800018D8
0x1800018d2  mov     rcx, rdi
0x1800018d5  mov     eax, r8d
0x1800018d8  mov     [rbp+90h+var_B8], eax
0x1800018db  mov     rax, [rbp+90h+arg_58]
0x1800018e2  mov     [rbp+90h+var_D0], rax
0x1800018e6  mov     rax, [rbp+90h+arg_50]
0x1800018ed  mov     [rbp+90h+var_C0], rcx
0x1800018f1  mov     [rbp+90h+var_B4], ebx
0x1800018f4  mov     [rbp+90h+var_C8], 4
0x1800018fc  mov     rcx, [rax]
0x1800018ff  test    rcx, rcx
0x180001902  jz      short loc_18000191A
0x180001904  mov     rax, rdx
0x180001907  inc     rax
0x18000190a  cmp     [rcx+rax*2], bx
0x18000190e  jnz     short loc_180001907
0x180001910  lea     r9d, ds:2[rax*2]
0x180001918  jmp     short loc_180001921
0x18000191a  lea     rcx, qword_1800125E0
0x180001921  mov     rax, [rbp+90h+arg_48]
0x180001928  mov     [rbp+90h+var_F0], rax
0x18000192c  mov     rax, [rbp+90h+arg_40]
0x180001933  mov     [rbp+90h+var_E0], rcx
0x180001937  mov     [rbp+90h+var_D8], r9d
0x18000193b  mov     [rbp+90h+var_D4], ebx
0x18000193e  mov     rcx, [rax]
0x180001941  mov     [rbp+90h+var_E8], 4
0x180001949  test    rcx, rcx
0x18000194c  jz      short loc_18000195D
0x18000194e  mov     rax, rdx
0x180001951  inc     rax
0x180001954  cmp     [rcx+rax], bl
0x180001957  jnz     short loc_180001951
0x180001959  inc     eax
0x18000195b  jmp     short loc_180001963
0x18000195d  mov     rcx, rdi
0x180001960  mov     eax, r8d
0x180001963  mov     [rbp+90h+var_F8], eax
0x180001966  mov     rax, [rbp+90h+arg_38]
0x18000196d  mov     [rbp+90h+var_110], rax
0x180001971  mov     rax, [rbp+90h+arg_30]
0x180001978  mov     [rbp+90h+var_100], rcx
0x18000197c  mov     [rbp+90h+var_F4], ebx
0x18000197f  mov     [rbp+90h+var_108], 4
0x180001987  mov     rcx, [rax]
0x18000198a  test    rcx, rcx
0x18000198d  jz      short loc_18000199D
0x18000198f  inc     rdx
0x180001992  cmp     [rcx+rdx], bl
0x180001995  jnz     short loc_18000198F
0x180001997  lea     r8d, [rdx+1]
0x18000199b  jmp     short loc_1800019A0
0x18000199d  mov     rcx, rdi
0x1800019a0  mov     rax, [rbp+90h+arg_28]
0x1800019a7  xor     r9d, r9d
0x1800019aa  mov     [rsp+190h+var_130], rax
0x1800019af  mov     rdx, r11
0x1800019b2  mov     rax, [rbp+90h+arg_20]
0x1800019b9  mov     [rsp+190h+var_140], rax
0x1800019be  lea     rax, [rsp+190h+var_160]
0x1800019c3  mov     [rsp+190h+var_120], rcx
0x1800019c8  mov     rcx, r10
0x1800019cb  mov     [rsp+190h+var_118], r8d
0x1800019d0  xor     r8d, r8d
0x1800019d3  mov     [rsp+190h+var_168], rax
0x1800019d8  mov     [rsp+190h+var_170], 14h
0x1800019e0  mov     [rsp+190h+var_114], ebx
0x1800019e4  mov     [rsp+190h+var_128], 4
0x1800019ed  mov     [rsp+190h+var_138], 8
0x1800019f6  call    _tlgWriteTransfer_EventWriteTransfer
0x1800019fb  mov     rcx, [rbp+90h+var_20]
0x1800019ff  xor     rcx, rsp; StackCookie
0x180001a02  call    __security_check_cookie
0x180001a07  mov     rbx, [rsp+190h+arg_10]
0x180001a0f  add     rsp, 180h
0x180001a16  pop     r14
0x180001a18  pop     rdi
0x180001a19  pop     rbp
0x180001a1a  retn
```
