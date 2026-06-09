# INTERNET_HANDLE_OBJECT::~INTERNET_HANDLE_OBJECT(void)

- ea: `0x1800ebbfc`
- end: `0x1800ebedd`
- name: `??1INTERNET_HANDLE_OBJECT@@UEAA@XZ`
- size: `737`
- prototype: `void __fastcall(INTERNET_HANDLE_OBJECT *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18007bbb8`
- `0x1800ebbc0`
- `0x18017b0e8`

## callees

- `0x180027ec0`
- `0x1800ebbfc`
- `0x1800ebee4`
- `0x1800ec578`
- `0x1800ec6e8`
- `0x1801358dc`
- `0x18014a3a4`
- `0x18018cba0`
- `0x1801e3c78`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ebcc7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ebcd4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ebd14`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ebcc7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ebcd4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ebd14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ebe35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ebe42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ebe35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ebe42`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ebdda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ebdf3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ebdda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ebdf3`

## pseudocode

```c
void __fastcall INTERNET_HANDLE_OBJECT::~INTERNET_HANDLE_OBJECT(INTERNET_HANDLE_OBJECT *this)
{
  CCancelFsmSyncList *v2; // rcx
  CPendingSyncCall *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx
  const char *v7; // rax
  void *v8; // rcx
  void *v9; // rcx
  char *v10; // rdi
  __int64 v11; // rcx
  char **v12; // rax
  const char *v13; // [rsp+20h] [rbp-18h] BYREF

  *(_QWORD *)this = &INTERNET_HANDLE_OBJECT::`vftable';
  if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
    WPP_SF_(1032, 31, WPP_a85fccec657a30c16cbc767298893445_Traceguids);
  v2 = (CCancelFsmSyncList *)*((_QWORD *)this + 70);
  if ( v2 )
  {
    CCancelFsmSyncList::Cancel(v2);
    v8 = (void *)*((_QWORD *)this + 70);
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
        operator delete(v8, 0x28u);
      *((_QWORD *)this + 70) = 0;
    }
  }
  if ( !*((_DWORD *)this + 66) )
  {
    v9 = (void *)*((_QWORD *)this + 31);
    if ( v9 )
      PP_FreeContext(v9);
    if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
      WPP_SF_(1032, 32, WPP_a85fccec657a30c16cbc767298893445_Traceguids);
    if ( *((_QWORD *)this + 36) )
    {
      if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
        WPP_SF_(1032, 33, WPP_a85fccec657a30c16cbc767298893445_Traceguids);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 36) + 16LL))(*((_QWORD *)this + 36));
      *((_QWORD *)this + 36) = 0;
    }
    EnterCriticalSection(&stru_180269B08);
    v10 = (char *)this + 432;
    if ( *(char **)v10 != v10 )
    {
      EnterCriticalSection(&stru_180269B08);
      v11 = *(_QWORD *)v10;
      if ( *(char **)(*(_QWORD *)v10 + 8LL) != v10 || (v12 = (char **)*((_QWORD *)this + 55), *v12 != v10) )
        __fastfail(3u);
      *v12 = (char *)v11;
      *(_QWORD *)(v11 + 8) = v12;
      --dword_180269B00;
      LeaveCriticalSection(&stru_180269B08);
    }
    LeaveCriticalSection(&stru_180269B08);
    GlobalPerSessionTerminate();
  }
  if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
    WPP_SF_(1032, 34, WPP_a85fccec657a30c16cbc767298893445_Traceguids);
  v3 = (CPendingSyncCall *)*((_QWORD *)this + 78);
  if ( v3 )
  {
    CPendingSyncCall::Release(v3);
    *((_QWORD *)this + 78) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 71);
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4, 0xFFFFFFFF) == 1 )
      operator delete(v4, 0x20u);
    *((_QWORD *)this + 71) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 70);
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5, 0xFFFFFFFF) == 1 )
      operator delete(v5, 0x28u);
    *((_QWORD *)this + 70) = 0;
  }
  v6 = *((_QWORD *)this + 57);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 57) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 368));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
  v7 = (const char *)*((_QWORD *)this + 34);
  v13 = v7;
  if ( v7 != String && v7 )
    WxFreeHeapEx(&v13);
  *((_QWORD *)this + 34) = String;
  *((_QWORD *)this + 35) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 5);
  HANDLE_OBJECT::~HANDLE_OBJECT(this);
}

```

## disassembly

```asm
0x1800ebbfc  mov     [rsp+arg_8], rbx
0x1800ebc01  push    rdi
0x1800ebc02  sub     rsp, 30h
0x1800ebc06  lea     rax, ??_7INTERNET_HANDLE_OBJECT@@6B@; const INTERNET_HANDLE_OBJECT::`vftable'
0x1800ebc0d  mov     rbx, rcx
0x1800ebc10  mov     [rcx], rax
0x1800ebc13  test    byte ptr cs:xmmword_180266B60+1, 1
0x1800ebc1a  jnz     loc_1800EBE52
0x1800ebc20  mov     rcx, [rbx+230h]; this
0x1800ebc27  test    rcx, rcx
0x1800ebc2a  jnz     loc_1800EBD2C
0x1800ebc30  cmp     dword ptr [rbx+108h], 0
0x1800ebc37  jz      loc_1800EBD81
0x1800ebc3d  test    byte ptr cs:xmmword_180266B60+1, 1
0x1800ebc44  jnz     loc_1800EBEAD
0x1800ebc4a  mov     rcx, [rbx+270h]; this
0x1800ebc51  test    rcx, rcx
0x1800ebc54  jnz     loc_1800EBEC8
0x1800ebc5a  mov     rcx, [rbx+238h]; void *
0x1800ebc61  test    rcx, rcx
0x1800ebc64  jz      short loc_1800EBC85
0x1800ebc66  or      eax, 0FFFFFFFFh
0x1800ebc69  lock xadd [rcx], eax
0x1800ebc6d  cmp     eax, 1
0x1800ebc70  jnz     short loc_1800EBC7A
0x1800ebc72  lea     edx, [rax+1Fh]; unsigned __int64
0x1800ebc75  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ebc7a  mov     qword ptr [rbx+238h], 0
0x1800ebc85  mov     rcx, [rbx+230h]; void *
0x1800ebc8c  test    rcx, rcx
0x1800ebc8f  jz      short loc_1800EBCB0
0x1800ebc91  or      eax, 0FFFFFFFFh
0x1800ebc94  lock xadd [rcx], eax
0x1800ebc98  cmp     eax, 1
0x1800ebc9b  jnz     short loc_1800EBCA5
0x1800ebc9d  lea     edx, [rax+27h]; unsigned __int64
0x1800ebca0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ebca5  mov     qword ptr [rbx+230h], 0
0x1800ebcb0  mov     rcx, [rbx+1C8h]
0x1800ebcb7  test    rcx, rcx
0x1800ebcba  jnz     loc_1800EBD65
0x1800ebcc0  lea     rcx, [rbx+170h]; lpCriticalSection
0x1800ebcc7  call    cs:__imp_DeleteCriticalSection
0x1800ebccd  lea     rcx, [rbx+128h]; lpCriticalSection
0x1800ebcd4  call    cs:__imp_DeleteCriticalSection
0x1800ebcda  mov     rax, [rbx+110h]
0x1800ebce1  lea     rdi, String
0x1800ebce8  mov     [rsp+38h+var_18], rax
0x1800ebced  cmp     rax, rdi
0x1800ebcf0  jz      short loc_1800EBCFB
0x1800ebcf2  test    rax, rax
0x1800ebcf5  jnz     loc_1800EBE12
0x1800ebcfb  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800ebd02  mov     [rbx+110h], rdi
0x1800ebd09  mov     qword ptr [rbx+118h], 0
0x1800ebd14  call    cs:__imp_DeleteCriticalSection
0x1800ebd1a  mov     rcx, rbx; this
0x1800ebd1d  mov     rbx, [rsp+38h+arg_8]
0x1800ebd22  add     rsp, 30h
0x1800ebd26  pop     rdi
0x1800ebd27  jmp     ??1HANDLE_OBJECT@@MEAA@XZ; HANDLE_OBJECT::~HANDLE_OBJECT(void)
0x1800ebd2c  call    ?Cancel@CCancelFsmSyncList@@QEAAXXZ; CCancelFsmSyncList::Cancel(void)
0x1800ebd31  mov     rcx, [rbx+230h]; void *
0x1800ebd38  test    rcx, rcx
0x1800ebd3b  jz      loc_1800EBC30
0x1800ebd41  or      eax, 0FFFFFFFFh
0x1800ebd44  lock xadd [rcx], eax
0x1800ebd48  cmp     eax, 1
0x1800ebd4b  jnz     short loc_1800EBD55
0x1800ebd4d  lea     edx, [rax+27h]; unsigned __int64
0x1800ebd50  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ebd55  mov     qword ptr [rbx+230h], 0
0x1800ebd60  jmp     loc_1800EBC30
0x1800ebd65  mov     rax, [rcx]
0x1800ebd68  mov     rax, [rax+10h]
0x1800ebd6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebd71  mov     qword ptr [rbx+1C8h], 0
0x1800ebd7c  jmp     loc_1800EBCC0
0x1800ebd81  mov     rcx, [rbx+0F8h]; void *
0x1800ebd88  test    rcx, rcx
0x1800ebd8b  jnz     loc_1800EBE6D
0x1800ebd91  test    byte ptr cs:xmmword_180266B60+1, 1
0x1800ebd98  jnz     loc_1800EBE77
0x1800ebd9e  cmp     qword ptr [rbx+120h], 0
0x1800ebda6  jz      short loc_1800EBDD3
0x1800ebda8  test    byte ptr cs:xmmword_180266B60+1, 1
0x1800ebdaf  jnz     loc_1800EBE92
0x1800ebdb5  mov     rcx, [rbx+120h]
0x1800ebdbc  mov     rax, [rcx]
0x1800ebdbf  mov     rax, [rax+10h]
0x1800ebdc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebdc8  mov     qword ptr [rbx+120h], 0
0x1800ebdd3  lea     rcx, stru_180269B08; lpCriticalSection
0x1800ebdda  call    cs:__imp_EnterCriticalSection
0x1800ebde0  lea     rdi, [rbx+1B0h]
0x1800ebde7  cmp     [rdi], rdi
0x1800ebdea  jz      short loc_1800EBE3B
0x1800ebdec  lea     rcx, stru_180269B08; lpCriticalSection
0x1800ebdf3  call    cs:__imp_EnterCriticalSection
0x1800ebdf9  mov     rcx, [rdi]
0x1800ebdfc  cmp     [rcx+8], rdi
0x1800ebe00  jnz     short loc_1800EBE0B
0x1800ebe02  mov     rax, [rdi+8]
0x1800ebe06  cmp     [rax], rdi
0x1800ebe09  jz      short loc_1800EBE21
0x1800ebe0b  mov     ecx, 3
0x1800ebe10  int     29h; Win8: RtlFailFast(ecx)
0x1800ebe12  lea     rcx, [rsp+38h+var_18]
0x1800ebe17  call    WxFreeHeapEx
0x1800ebe1c  jmp     loc_1800EBCFB
0x1800ebe21  mov     [rax], rcx
0x1800ebe24  mov     [rcx+8], rax
0x1800ebe28  lea     rcx, stru_180269B08; lpCriticalSection
0x1800ebe2f  dec     cs:dword_180269B00
0x1800ebe35  call    cs:__imp_LeaveCriticalSection
0x1800ebe3b  lea     rcx, stru_180269B08; lpCriticalSection
0x1800ebe42  call    cs:__imp_LeaveCriticalSection
0x1800ebe48  call    GlobalPerSessionTerminate
0x1800ebe4d  jmp     loc_1800EBC3D
0x1800ebe52  mov     edx, 1Fh
0x1800ebe57  lea     r8, WPP_a85fccec657a30c16cbc767298893445_Traceguids
0x1800ebe5e  mov     ecx, 408h
0x1800ebe63  call    WPP_SF_
0x1800ebe68  jmp     loc_1800EBC20
0x1800ebe6d  call    ?PP_FreeContext@@YAXPEAX@Z; PP_FreeContext(void *)
0x1800ebe72  jmp     loc_1800EBD91
0x1800ebe77  mov     edx, 20h ; ' '
0x1800ebe7c  lea     r8, WPP_a85fccec657a30c16cbc767298893445_Traceguids
0x1800ebe83  mov     ecx, 408h
0x1800ebe88  call    WPP_SF_
0x1800ebe8d  jmp     loc_1800EBD9E
0x1800ebe92  mov     edx, 21h ; '!'
0x1800ebe97  lea     r8, WPP_a85fccec657a30c16cbc767298893445_Traceguids
0x1800ebe9e  mov     ecx, 408h
0x1800ebea3  call    WPP_SF_
0x1800ebea8  jmp     loc_1800EBDB5
0x1800ebead  mov     edx, 22h ; '"'
0x1800ebeb2  lea     r8, WPP_a85fccec657a30c16cbc767298893445_Traceguids
0x1800ebeb9  mov     ecx, 408h
0x1800ebebe  call    WPP_SF_
0x1800ebec3  jmp     loc_1800EBC4A
0x1800ebec8  call    ?Release@CPendingSyncCall@@QEAAKXZ; CPendingSyncCall::Release(void)
0x1800ebecd  mov     qword ptr [rbx+270h], 0
0x1800ebed8  jmp     loc_1800EBC5A
```
