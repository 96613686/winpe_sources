# CHttp2Stream::OpenStream(_HK_PAIR *,ulong,int,ulong,ulong,void (*)(void *,ulong,ulong),void *)

- ea: `0x18002ec54`
- end: `0x18002efea`
- name: `?OpenStream@CHttp2Stream@@AEAAJPEAU_HK_PAIR@@KHKKP6AXPEAXKK@Z1@Z`
- size: `918`
- prototype: `__int64 __usercall@<rax>(CHttp2Stream *__hidden this@<rcx>, struct _HK_PAIR *@<rdx>, unsigned int@<r8d>, int@<r9d>, unsigned int, unsigned int, void (*)(void *, unsigned int, unsigned int), void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800640c8`

## callees

- `0x18002da00`
- `0x18002db48`
- `0x18002e2c4`
- `0x18002e68c`
- `0x18002eb98`
- `0x18002ec54`
- `0x18002f4d0`
- `0x180034504`
- `0x180072c70`
- `0x18007309c`
- `0x1800971ec`
- `0x1800974fc`
- `0x18009770c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ecb7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ecb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ee1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eede`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ee1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eede`

## pseudocode

```c
__int64 __fastcall CHttp2Stream::OpenStream(
        CHttp2Stream *this,
        struct _HK_PAIR *a2,
        unsigned int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        void (*a7)(void *, unsigned int, unsigned int),
        void *a8)
{
  struct CHttp2SendContext *v12; // rdi
  int v13; // edx
  signed int IsAborted; // esi
  int v15; // r8d
  int v16; // eax
  __int64 v17; // r9
  unsigned int v18; // r15d
  __int64 v19; // rdx
  __int64 v20; // rcx
  CHttp2SendContext *v21; // rax
  CHttp2SendContext *v22; // rbx
  CHttp2SendContext *v23; // rax
  CHttp2SendContext *v24; // rbx
  int WorkItem; // eax
  CHttp2Stream *v26; // rcx
  int v27; // eax
  CHttp2 *v28; // rcx
  unsigned int v29; // ebx
  struct CHttp2SendContext *v31; // [rsp+60h] [rbp-58h] BYREF
  int v32; // [rsp+68h] [rbp-50h]
  int v33; // [rsp+6Ch] [rbp-4Ch]
  void *v34; // [rsp+70h] [rbp-48h]

  v34 = a8;
  v33 = 0;
  v12 = 0;
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_qqdldd((_DWORD)this, 28, a3, (_DWORD)this, (__int64)a2);
  if ( this )
    _InterlockedIncrement((volatile signed __int32 *)this);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  if ( *((_DWORD *)this + 47) )
  {
    IsAborted = -2147023537;
    v33 = 882;
    goto LABEL_31;
  }
  *((_DWORD *)this + 47) = 1;
  IsAborted = CHttp2Stream::IsAborted(this);
  if ( IsAborted < 0 )
  {
    v33 = 892;
    goto LABEL_31;
  }
  v16 = *((_DWORD *)this + 49);
  v17 = *((_QWORD *)this + 1);
  *((_DWORD *)this + 39) = a5;
  *((_DWORD *)this + 40) = a6;
  v32 = v16;
  HIDWORD(v31) = 0;
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_qqqdldqq((_DWORD)v34, v13, v15, v17, (__int64)this, (__int64)a2, a3, a4, v16);
  v18 = 0;
  v19 = 0;
  if ( !a3 )
    goto LABEL_12;
  do
  {
    v20 = 3 * v19;
    v19 = (unsigned int)(v19 + 1);
    v18 += *((_DWORD *)a2 + 2 * v20 + 4) + *((_DWORD *)a2 + 2 * v20 + 5);
  }
  while ( (unsigned int)v19 < a3 );
  if ( v18 >= 0x100000 )
  {
    IsAborted = -2147024785;
    HIDWORD(v31) = 3380;
  }
  else
  {
LABEL_12:
    HIDWORD(v31) = 0;
    v21 = (CHttp2SendContext *)operator new(0x98u);
    v22 = v21;
    if ( v21 && (memset_0(v21, 0, 0x98u), v23 = CHttp2SendContext::CHttp2SendContext(v22), (v24 = v23) != 0) )
    {
      *((_DWORD *)v23 + 1) = 1;
      WorkItem = WxH2UserCreateWorkItem(
                   (_QWORD *)v23 + 7,
                   (__int64)CHttp2SendContext::StaticWorkItemCallback,
                   (__int64)v23);
      IsAborted = WorkItem;
      if ( WorkItem > 0 )
        IsAborted = (unsigned __int16)WorkItem | 0x80070000;
      if ( IsAborted >= 0 )
      {
        *((_QWORD *)v24 + 11) = a2;
        *((_DWORD *)v24 + 24) = a3;
        _InterlockedIncrement((volatile signed __int32 *)this);
        v26 = (CHttp2Stream *)*((_QWORD *)v24 + 8);
        if ( v26 )
          CHttp2Stream::Release(v26);
        v27 = v32;
        v12 = v24;
        *((_QWORD *)v24 + 8) = this;
        *((_DWORD *)v24 + 19) = v27;
        *((_QWORD *)v24 + 4) = WapHttp2StreamSendHeadersCompletionRoutine;
        *((_QWORD *)v24 + 5) = v34;
        *((_DWORD *)v24 + 18) = a4;
        *((_DWORD *)v24 + 29) = v18;
        goto LABEL_20;
      }
      HIDWORD(v31) = 236;
      CHttp2SendContext::Release(v24);
    }
    else
    {
      HIDWORD(v31) = 224;
      IsAborted = -2147024882;
    }
    HIDWORD(v31) = 3383;
  }
LABEL_20:
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_d(1050, 84, WPP_1eba17a514423a0ebe5ee43bce786d1b_Traceguids, (unsigned int)IsAborted);
  if ( IsAborted >= 0 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    v28 = (CHttp2 *)*((_QWORD *)this + 1);
    v31 = v12;
    v12 = 0;
    CHttp2::SendContext(v28, this, &v31);
    IsAborted = -2147023899;
    v33 = 927;
    v29 = -2147023899;
    goto LABEL_24;
  }
  v33 = 908;
LABEL_31:
  v29 = IsAborted;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  if ( (int)(IsAborted + 0x80000000) >= 0 && IsAborted != -2147023899 )
    CHttp2Stream::AbortHr(this, IsAborted, 8u);
LABEL_24:
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_d(1050, 29, WPP_a7f56d08f8993c62676a3a151a0e9be5_Traceguids, (unsigned int)IsAborted);
  if ( v12 )
    CHttp2SendContext::Release(v12);
  CHttp2Stream::Release(this);
  return v29;
}

```

## disassembly

```asm
0x18002ec54  mov     [rsp+arg_10], rbx
0x18002ec59  push    rbp
0x18002ec5a  push    rsi
0x18002ec5b  push    rdi
0x18002ec5c  push    r12
0x18002ec5e  push    r13
0x18002ec60  push    r14
0x18002ec62  push    r15
0x18002ec64  sub     rsp, 80h
0x18002ec6b  mov     rax, [rsp+0B8h+arg_38]
0x18002ec73  mov     r13d, r9d
0x18002ec76  mov     [rsp+0B8h+var_48], rax
0x18002ec7b  mov     r14d, r8d
0x18002ec7e  mov     r12, rdx
0x18002ec81  mov     [rsp+0B8h+var_4C], 0
0x18002ec89  mov     rbp, rcx
0x18002ec8c  xor     edi, edi
0x18002ec8e  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18002ec95  mov     ebx, [rsp+0B8h+arg_28]
0x18002ec9c  mov     r15d, [rsp+0B8h+arg_20]
0x18002eca4  jnz     loc_18002EEAE
0x18002ecaa  test    rbp, rbp
0x18002ecad  jz      short loc_18002ECB3
0x18002ecaf  lock inc dword ptr [rbp+0]
0x18002ecb3  lea     rcx, [rbp+68h]; lpCriticalSection
0x18002ecb7  call    cs:__imp_EnterCriticalSection
0x18002ecbe  nop     dword ptr [rax+rax+00h]
0x18002ecc3  cmp     [rbp+0BCh], edi
0x18002ecc9  jnz     loc_18002EF1B
0x18002eccf  mov     rcx, rbp; this
0x18002ecd2  mov     dword ptr [rbp+0BCh], 1
0x18002ecdc  call    ?IsAborted@CHttp2Stream@@AEAAJXZ; CHttp2Stream::IsAborted(void)
0x18002ece1  mov     esi, eax
0x18002ece3  test    eax, eax
0x18002ece5  js      loc_18002EF2A
0x18002eceb  mov     eax, [rbp+0C4h]
0x18002ecf1  mov     r9, [rbp+8]
0x18002ecf5  mov     [rbp+9Ch], r15d
0x18002ecfc  mov     [rbp+0A0h], ebx
0x18002ed02  mov     [rsp+0B8h+var_50], eax
0x18002ed06  mov     dword ptr [rsp+0B8h+var_58+4], edi
0x18002ed0a  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18002ed11  jnz     loc_18002EF34
0x18002ed17  xor     r15d, r15d
0x18002ed1a  xor     edx, edx
0x18002ed1c  test    r14d, r14d
0x18002ed1f  jz      short loc_18002ED46
0x18002ed21  lea     rcx, [rdx+rdx*2]
0x18002ed25  inc     edx
0x18002ed27  mov     eax, [r12+rcx*8+14h]
0x18002ed2c  add     eax, [r12+rcx*8+10h]
0x18002ed31  add     r15d, eax
0x18002ed34  cmp     edx, r14d
0x18002ed37  jb      short loc_18002ED21
0x18002ed39  cmp     r15d, 100000h
0x18002ed40  jnb     loc_18002EF60
0x18002ed46  mov     esi, 98h
0x18002ed4b  mov     dword ptr [rsp+0B8h+var_58+4], edi
0x18002ed4f  mov     ecx, esi; Size
0x18002ed51  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ed56  mov     rbx, rax
0x18002ed59  test    rax, rax
0x18002ed5c  jz      loc_18002EE8A
0x18002ed62  mov     r8d, esi; Size
0x18002ed65  xor     edx, edx; Val
0x18002ed67  mov     rcx, rax; void *
0x18002ed6a  call    memset_0
0x18002ed6f  mov     rcx, rbx; this
0x18002ed72  call    ??0CHttp2SendContext@@AEAA@XZ; CHttp2SendContext::CHttp2SendContext(void)
0x18002ed77  mov     rbx, rax
0x18002ed7a  test    rax, rax
0x18002ed7d  jz      loc_18002EE8A
0x18002ed83  lea     rcx, [rax+38h]
0x18002ed87  mov     dword ptr [rax+4], 1
0x18002ed8e  mov     r8, rax
0x18002ed91  lea     rdx, ?StaticWorkItemCallback@CHttp2SendContext@@CAXPEAX0@Z; CHttp2SendContext::StaticWorkItemCallback(void *,void *)
0x18002ed98  call    WxH2UserCreateWorkItem
0x18002ed9d  mov     esi, eax
0x18002ed9f  test    eax, eax
0x18002eda1  jle     short loc_18002EDAC
0x18002eda3  movzx   esi, ax
0x18002eda6  or      esi, 80070000h
0x18002edac  test    esi, esi
0x18002edae  js      loc_18002EF72
0x18002edb4  mov     [rbx+58h], r12
0x18002edb8  mov     [rbx+60h], r14d
0x18002edbc  lock inc dword ptr [rbp+0]
0x18002edc0  mov     rcx, [rbx+40h]; this
0x18002edc4  test    rcx, rcx
0x18002edc7  jnz     loc_18002EEA4
0x18002edcd  mov     eax, [rsp+0B8h+var_50]
0x18002edd1  mov     rdi, rbx
0x18002edd4  mov     [rbx+40h], rbp
0x18002edd8  mov     [rbx+4Ch], eax
0x18002eddb  lea     rax, WapHttp2StreamSendHeadersCompletionRoutine
0x18002ede2  mov     [rbx+20h], rax
0x18002ede6  mov     rax, [rsp+0B8h+var_48]
0x18002edeb  mov     [rbx+28h], rax
0x18002edef  mov     [rbx+48h], r13d
0x18002edf3  mov     [rbx+74h], r15d
0x18002edf7  xor     ebx, ebx
0x18002edf9  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18002ee00  jnz     loc_18002EF87
0x18002ee06  test    rbx, rbx
0x18002ee09  jnz     loc_18002EFA5
0x18002ee0f  test    esi, esi
0x18002ee11  js      loc_18002EFB2
0x18002ee17  lea     rcx, [rbp+68h]; lpCriticalSection
0x18002ee1b  call    cs:__imp_LeaveCriticalSection
0x18002ee22  nop     dword ptr [rax+rax+00h]
0x18002ee27  mov     rcx, [rbp+8]; this
0x18002ee2b  lea     r8, [rsp+0B8h+var_58]; struct CHttp2SendContext **
0x18002ee30  mov     [rsp+0B8h+var_58], rdi
0x18002ee35  mov     rdx, rbp; struct CHttp2Stream *
0x18002ee38  xor     edi, edi
0x18002ee3a  call    ?SendContext@CHttp2@@AEAAXPEAVCHttp2Stream@@PEAPEAVCHttp2SendContext@@@Z; CHttp2::SendContext(CHttp2Stream *,CHttp2SendContext * *)
0x18002ee3f  mov     esi, 800703E5h
0x18002ee44  mov     [rsp+0B8h+var_4C], 39Fh
0x18002ee4c  mov     ebx, esi
0x18002ee4e  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18002ee55  jnz     loc_18002EFBF
0x18002ee5b  test    rdi, rdi
0x18002ee5e  jnz     loc_18002EFDD
0x18002ee64  mov     rcx, rbp; this
0x18002ee67  call    ?Release@CHttp2Stream@@QEAAKXZ; CHttp2Stream::Release(void)
0x18002ee6c  mov     eax, ebx
0x18002ee6e  mov     rbx, [rsp+0B8h+arg_10]
0x18002ee76  add     rsp, 80h
0x18002ee7d  pop     r15
0x18002ee7f  pop     r14
0x18002ee81  pop     r13
0x18002ee83  pop     r12
0x18002ee85  pop     rdi
0x18002ee86  pop     rsi
0x18002ee87  pop     rbp
0x18002ee88  retn
0x18002ee8a  mov     dword ptr [rsp+0B8h+var_58+4], 0E0h
0x18002ee92  mov     esi, 8007000Eh
0x18002ee97  mov     dword ptr [rsp+0B8h+var_58+4], 0D37h
0x18002ee9f  jmp     loc_18002EDF7
0x18002eea4  call    ?Release@CHttp2Stream@@QEAAKXZ; CHttp2Stream::Release(void)
0x18002eea9  jmp     loc_18002EDCD
0x18002eeae  mov     [rsp+0B8h+var_78], ebx
0x18002eeb2  mov     edx, 1Ch
0x18002eeb7  mov     [rsp+0B8h+var_80], r15d
0x18002eebc  mov     r9, rbp
0x18002eebf  mov     [rsp+0B8h+var_88], r13d
0x18002eec4  mov     dword ptr [rsp+0B8h+var_90], r14d
0x18002eec9  mov     [rsp+0B8h+var_98], r12
0x18002eece  call    WPP_SF_qqdldd
0x18002eed3  jmp     loc_18002ECAA
0x18002eed8  lea     rcx, [rbp+68h]; lpCriticalSection
0x18002eedc  mov     ebx, esi
0x18002eede  call    cs:__imp_LeaveCriticalSection
0x18002eee5  nop     dword ptr [rax+rax+00h]
0x18002eeea  mov     ecx, 80000000h
0x18002eeef  lea     eax, [rbx+rcx]
0x18002eef2  test    ecx, eax
0x18002eef4  jnz     loc_18002EE4E
0x18002eefa  cmp     ebx, 800703E5h
0x18002ef00  jz      loc_18002EE4E
0x18002ef06  mov     r8d, 8; unsigned int
0x18002ef0c  mov     edx, esi; int
0x18002ef0e  mov     rcx, rbp; this
0x18002ef11  call    ?AbortHr@CHttp2Stream@@QEAAHJK@Z; CHttp2Stream::AbortHr(long,ulong)
0x18002ef16  jmp     loc_18002EE4E
0x18002ef1b  mov     esi, 8007054Fh
0x18002ef20  mov     [rsp+0B8h+var_4C], 372h
0x18002ef28  jmp     short loc_18002EED8
0x18002ef2a  mov     [rsp+0B8h+var_4C], 37Ch
0x18002ef32  jmp     short loc_18002EED8
0x18002ef34  mov     rcx, [rsp+0B8h+var_48]
0x18002ef39  mov     [rsp+0B8h+var_68], rcx
0x18002ef3e  mov     [rsp+0B8h+var_78], eax
0x18002ef42  mov     [rsp+0B8h+var_80], r13d
0x18002ef47  mov     [rsp+0B8h+var_88], r14d
0x18002ef4c  mov     [rsp+0B8h+var_90], r12
0x18002ef51  mov     [rsp+0B8h+var_98], rbp
0x18002ef56  call    WPP_SF_qqqdldqq
0x18002ef5b  jmp     loc_18002ED17
0x18002ef60  mov     esi, 8007006Fh
0x18002ef65  mov     dword ptr [rsp+0B8h+var_58+4], 0D34h
0x18002ef6d  jmp     loc_18002EDF7
0x18002ef72  mov     rcx, rbx; this
0x18002ef75  mov     dword ptr [rsp+0B8h+var_58+4], 0ECh
0x18002ef7d  call    ?Release@CHttp2SendContext@@QEAAKXZ; CHttp2SendContext::Release(void)
0x18002ef82  jmp     loc_18002EE97
0x18002ef87  mov     edx, 54h ; 'T'
0x18002ef8c  lea     r8, WPP_1eba17a514423a0ebe5ee43bce786d1b_Traceguids
0x18002ef93  mov     ecx, 41Ah
0x18002ef98  mov     r9d, esi
0x18002ef9b  call    WPP_SF_d
0x18002efa0  jmp     loc_18002EE06
0x18002efa5  mov     rcx, rbx; this
0x18002efa8  call    ?Release@CHttp2SendContext@@QEAAKXZ; CHttp2SendContext::Release(void)
0x18002efad  jmp     loc_18002EE0F
0x18002efb2  mov     [rsp+0B8h+var_4C], 38Ch
0x18002efba  jmp     loc_18002EED8
0x18002efbf  mov     edx, 1Dh
0x18002efc4  lea     r8, WPP_a7f56d08f8993c62676a3a151a0e9be5_Traceguids
0x18002efcb  mov     ecx, 41Ah
0x18002efd0  mov     r9d, esi
0x18002efd3  call    WPP_SF_d
0x18002efd8  jmp     loc_18002EE5B
0x18002efdd  mov     rcx, rdi; this
0x18002efe0  call    ?Release@CHttp2SendContext@@QEAAKXZ; CHttp2SendContext::Release(void)
0x18002efe5  jmp     loc_18002EE64
```
