# TLPCMgr::TClientInfo::CreateInstance(unsigned __int64 const &,TLPCMgr::TWorkCrewForUniqueProcess &)

- ea: `0x140010f8c`
- end: `0x1400111fa`
- name: `?CreateInstance@TClientInfo@TLPCMgr@@SAPEAV12@AEB_KAEAVTWorkCrewForUniqueProcess@2@@Z`
- size: `622`
- prototype: `struct TLPCMgr::TClientInfo *__fastcall(const unsigned __int64 *, struct TLPCMgr::TWorkCrewForUniqueProcess *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140011624`

## callees

- `0x140001b50`
- `0x1400101dc`
- `0x1400102d8`
- `0x140010f8c`
- `0x14001140c`
- `0x1400141ac`
- `0x140016010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140011123`
- `KERNEL32!CloseHandle` at `0x140011123`
- `KERNEL32!CreateEventW` at `0x1400110b4`
- `KERNEL32!CreateEventW` at `0x1400110b4`

## pseudocode

```c
struct TLPCMgr::TClientInfo *__fastcall TLPCMgr::TClientInfo::CreateInstance(
        const unsigned __int64 *a1,
        struct TLPCMgr::TWorkCrewForUniqueProcess *a2)
{
  int Element; // eax
  volatile signed __int32 *v5; // rbx
  TLPCMgr::TClientInfo *v6; // rax
  __int64 v7; // rsi
  signed __int32 v8; // edx
  signed __int32 v9; // edx
  HANDLE EventW; // rsi
  TLPCMgr::TDispatcher *v11; // rax
  TLPCMgr::TClientInfo *v12; // rax
  signed __int32 v14; // edx
  struct NAdvancedLibrary::THashElementBase *v15; // [rsp+50h] [rbp+8h] BYREF
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF

  v16 = *(unsigned int *)a1;
  v15 = 0;
  Element = NAdvancedLibrary::THashTableBase::FindElement(
              (struct TLPCMgr::TWorkCrewForUniqueProcess *)((char *)a2 + 232),
              &v16,
              &v15);
  if ( Element < 0 )
  {
LABEL_17:
    if ( Element == 1 )
      goto LABEL_18;
    return 0;
  }
  if ( !v15 )
  {
    Element = 1;
    goto LABEL_17;
  }
  v5 = (volatile signed __int32 *)*((_QWORD *)v15 + 4);
  v6 = (TLPCMgr::TClientInfo *)operator new(0x70u);
  if ( !v6 || (v7 = TLPCMgr::TClientInfo::TClientInfo(v6, a1, (struct TLPCMgr::TDispatcher *)v5)) == 0 )
  {
    if ( v5 )
    {
      do
        v9 = *((_DWORD *)v5 + 2);
      while ( v9 != 0x7FFFFFFF && v9 != _InterlockedCompareExchange(v5 + 2, v9 - 1, v9) );
      goto LABEL_33;
    }
    return 0;
  }
  if ( _InterlockedIncrement(v5 + 24) != 1 )
    goto LABEL_36;
  --*((_DWORD *)v5 + 24);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  do
    v8 = *((_DWORD *)v5 + 2);
  while ( v8 != 0x7FFFFFFF && v8 != _InterlockedCompareExchange(v5 + 2, v8 - 1, v8) );
  if ( v8 == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
LABEL_18:
  EventW = CreateEventW(0, 0, 0, 0);
  v11 = (TLPCMgr::TDispatcher *)operator new(0xF0u);
  if ( v11 )
    v5 = (volatile signed __int32 *)TLPCMgr::TDispatcher::TDispatcher(v11, *(unsigned int *)a1, EventW);
  else
    v5 = 0;
  if ( !v5 )
  {
    if ( EventW )
      CloseHandle(EventW);
    return 0;
  }
  TLPCMgr::TDispatcher::Initialize((TLPCMgr::TDispatcher *)v5, a2);
  v12 = (TLPCMgr::TClientInfo *)operator new(0x70u);
  if ( v12 )
    v7 = TLPCMgr::TClientInfo::TClientInfo(v12, a1, (struct TLPCMgr::TDispatcher *)v5);
  else
    v7 = 0;
  if ( !v7 )
  {
    do
      v9 = *((_DWORD *)v5 + 2);
    while ( v9 != 0x7FFFFFFF && v9 != _InterlockedCompareExchange(v5 + 2, v9 - 1, v9) );
LABEL_33:
    if ( v9 == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    return 0;
  }
LABEL_36:
  if ( v5 )
  {
    do
      v14 = *((_DWORD *)v5 + 2);
    while ( v14 != 0x7FFFFFFF && v14 != _InterlockedCompareExchange(v5 + 2, v14 - 1, v14) );
    if ( v14 == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
  }
  return (struct TLPCMgr::TClientInfo *)v7;
}

```

## disassembly

```asm
0x140010f8c  mov     r11, rsp
0x140010f8f  mov     [r11+18h], rbx
0x140010f93  push    rbp
0x140010f94  push    rsi
0x140010f95  push    rdi
0x140010f96  push    r12
0x140010f98  push    r14
0x140010f9a  sub     rsp, 20h
0x140010f9e  mov     eax, [rcx]
0x140010fa0  lea     r8, [r11+8]; struct NAdvancedLibrary::THashElementBase **
0x140010fa4  mov     rbp, rcx
0x140010fa7  mov     [r11+10h], rax
0x140010fab  lea     rcx, [rdx+0E8h]; this
0x140010fb2  mov     r14, rdx
0x140010fb5  xor     ebx, ebx
0x140010fb7  lea     rdx, [r11+10h]; void *
0x140010fbb  mov     [r11+8], rbx
0x140010fbf  call    ?FindElement@THashTableBase@NAdvancedLibrary@@QEBAJPEBXPEAPEAVTHashElementBase@2@@Z; NAdvancedLibrary::THashTableBase::FindElement(void const *,NAdvancedLibrary::THashElementBase * *)
0x140010fc4  mov     r12d, 7FFFFFFFh
0x140010fca  test    eax, eax
0x140010fcc  js      loc_14001109E
0x140010fd2  mov     rax, [rsp+48h+arg_0]
0x140010fd7  xor     ecx, ecx
0x140010fd9  test    rax, rax
0x140010fdc  setnz   cl
0x140010fdf  test    rax, rax
0x140010fe2  jz      short loc_140010FE8
0x140010fe4  mov     rbx, [rax+20h]
0x140010fe8  test    ecx, ecx
0x140010fea  jz      loc_140011099
0x140010ff0  mov     ecx, 70h ; 'p'; Size
0x140010ff5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140010ffa  test    rax, rax
0x140010ffd  jz      short loc_140011071
0x140010fff  mov     r8, rbx; struct TLPCMgr::TDispatcher *
0x140011002  mov     rdx, rbp; unsigned __int64 *
0x140011005  mov     rcx, rax; this
0x140011008  call    ??0TClientInfo@TLPCMgr@@AEAA@AEB_KPEAVTDispatcher@1@@Z; TLPCMgr::TClientInfo::TClientInfo(unsigned __int64 const &,TLPCMgr::TDispatcher *)
0x14001100d  mov     rsi, rax
0x140011010  test    rax, rax
0x140011013  jz      short loc_140011071
0x140011015  mov     eax, 1
0x14001101a  lock xadd [rbx+60h], eax
0x14001101f  inc     eax
0x140011021  cmp     eax, 1
0x140011024  jnz     loc_1400111B5
0x14001102a  mov     eax, [rbx+60h]
0x14001102d  mov     rcx, rsi
0x140011030  dec     eax
0x140011032  mov     [rbx+60h], eax
0x140011035  mov     rax, [rsi]
0x140011038  mov     rax, [rax+10h]
0x14001103c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011041  xor     edi, edi
0x140011043  jmp     short loc_140011051
0x140011045  lea     ecx, [rdx-1]
0x140011048  mov     eax, edx
0x14001104a  lock cmpxchg [rbx+8], ecx
0x14001104f  jz      short loc_140011059
0x140011051  mov     edx, [rbx+8]
0x140011054  cmp     edx, r12d
0x140011057  jnz     short loc_140011045
0x140011059  lea     eax, [rdx-1]
0x14001105c  test    eax, eax
0x14001105e  jnz     short loc_1400110AA
0x140011060  mov     rax, [rbx]
0x140011063  mov     rcx, rbx
0x140011066  mov     rax, [rax+8]
0x14001106a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001106f  jmp     short loc_1400110AA
0x140011071  test    rbx, rbx
0x140011074  jz      loc_1400111AF
0x14001107a  jmp     short loc_14001108C
0x14001107c  lea     ecx, [rdx-1]
0x14001107f  mov     eax, edx
0x140011081  lock cmpxchg [rbx+8], ecx
0x140011086  jz      loc_140011199
0x14001108c  mov     edx, [rbx+8]
0x14001108f  cmp     edx, r12d
0x140011092  jnz     short loc_14001107C
0x140011094  jmp     loc_140011199
0x140011099  mov     eax, 1
0x14001109e  mov     rdi, rbx
0x1400110a1  cmp     eax, 1
0x1400110a4  jnz     loc_14001117A
0x1400110aa  xor     r9d, r9d; lpName
0x1400110ad  xor     r8d, r8d; bInitialState
0x1400110b0  xor     edx, edx; bManualReset
0x1400110b2  xor     ecx, ecx; lpEventAttributes
0x1400110b4  call    cs:__imp_CreateEventW
0x1400110ba  mov     ecx, 0F0h; Size
0x1400110bf  mov     rsi, rax
0x1400110c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400110c7  test    rax, rax
0x1400110ca  jz      short loc_1400110DF
0x1400110cc  mov     edx, [rbp+0]; unsigned __int64
0x1400110cf  mov     r8, rsi; void *
0x1400110d2  mov     rcx, rax; this
0x1400110d5  call    ??0TDispatcher@TLPCMgr@@QEAA@_KPEAX@Z; TLPCMgr::TDispatcher::TDispatcher(unsigned __int64,void *)
0x1400110da  mov     rbx, rax
0x1400110dd  jmp     short loc_1400110E1
0x1400110df  xor     ebx, ebx
0x1400110e1  test    rdi, rdi
0x1400110e4  jz      short loc_140011112
0x1400110e6  jmp     short loc_1400110F4
0x1400110e8  lea     ecx, [rdx-1]
0x1400110eb  mov     eax, edx
0x1400110ed  lock cmpxchg [rdi+8], ecx
0x1400110f2  jz      short loc_1400110FC
0x1400110f4  mov     edx, [rdi+8]
0x1400110f7  cmp     edx, r12d
0x1400110fa  jnz     short loc_1400110E8
0x1400110fc  lea     eax, [rdx-1]
0x1400110ff  test    eax, eax
0x140011101  jnz     short loc_140011112
0x140011103  mov     rax, [rdi]
0x140011106  mov     rcx, rdi
0x140011109  mov     rax, [rax+8]
0x14001110d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011112  test    rbx, rbx
0x140011115  jnz     short loc_14001112E
0x140011117  test    rsi, rsi
0x14001111a  jz      loc_1400111AF
0x140011120  mov     rcx, rsi; hObject
0x140011123  call    cs:__imp_CloseHandle
0x140011129  jmp     loc_1400111AF
0x14001112e  mov     rdx, r14; struct TLPCMgr::TWorkCrewForUniqueProcess *
0x140011131  mov     rcx, rbx; this
0x140011134  call    ?Initialize@TDispatcher@TLPCMgr@@QEAAJPEAVTWorkCrewForUniqueProcess@2@@Z; TLPCMgr::TDispatcher::Initialize(TLPCMgr::TWorkCrewForUniqueProcess *)
0x140011139  mov     ecx, 70h ; 'p'; Size
0x14001113e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140011143  test    rax, rax
0x140011146  jz      short loc_14001115B
0x140011148  mov     r8, rbx; struct TLPCMgr::TDispatcher *
0x14001114b  mov     rdx, rbp; unsigned __int64 *
0x14001114e  mov     rcx, rax; this
0x140011151  call    ??0TClientInfo@TLPCMgr@@AEAA@AEB_KPEAVTDispatcher@1@@Z; TLPCMgr::TClientInfo::TClientInfo(unsigned __int64 const &,TLPCMgr::TDispatcher *)
0x140011156  mov     rsi, rax
0x140011159  jmp     short loc_14001115D
0x14001115b  xor     esi, esi
0x14001115d  test    rsi, rsi
0x140011160  jnz     short loc_1400111B5
0x140011162  jmp     short loc_140011170
0x140011164  lea     ecx, [rdx-1]
0x140011167  mov     eax, edx
0x140011169  lock cmpxchg [rbx+8], ecx
0x14001116e  jz      short loc_140011199
0x140011170  mov     edx, [rbx+8]
0x140011173  cmp     edx, r12d
0x140011176  jnz     short loc_140011164
0x140011178  jmp     short loc_140011199
0x14001117a  test    eax, eax
0x14001117c  jns     short loc_1400111B3
0x14001117e  test    rbx, rbx
0x140011181  jz      short loc_1400111AF
0x140011183  jmp     short loc_140011191
0x140011185  lea     ecx, [rdx-1]
0x140011188  mov     eax, edx
0x14001118a  lock cmpxchg [rbx+8], ecx
0x14001118f  jz      short loc_140011199
0x140011191  mov     edx, [rbx+8]
0x140011194  cmp     edx, r12d
0x140011197  jnz     short loc_140011185
0x140011199  lea     eax, [rdx-1]
0x14001119c  test    eax, eax
0x14001119e  jnz     short loc_1400111AF
0x1400111a0  mov     rax, [rbx]
0x1400111a3  mov     rcx, rbx
0x1400111a6  mov     rax, [rax+8]
0x1400111aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400111af  xor     eax, eax
0x1400111b1  jmp     short loc_1400111E9
0x1400111b3  xor     esi, esi
0x1400111b5  test    rbx, rbx
0x1400111b8  jz      short loc_1400111E6
0x1400111ba  jmp     short loc_1400111C8
0x1400111bc  lea     ecx, [rdx-1]
0x1400111bf  mov     eax, edx
0x1400111c1  lock cmpxchg [rbx+8], ecx
0x1400111c6  jz      short loc_1400111D0
0x1400111c8  mov     edx, [rbx+8]
0x1400111cb  cmp     edx, r12d
0x1400111ce  jnz     short loc_1400111BC
0x1400111d0  lea     eax, [rdx-1]
0x1400111d3  test    eax, eax
0x1400111d5  jnz     short loc_1400111E6
0x1400111d7  mov     rax, [rbx]
0x1400111da  mov     rcx, rbx
0x1400111dd  mov     rax, [rax+8]
0x1400111e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400111e6  mov     rax, rsi
0x1400111e9  mov     rbx, [rsp+48h+arg_10]
0x1400111ee  add     rsp, 20h
0x1400111f2  pop     r14
0x1400111f4  pop     r12
0x1400111f6  pop     rdi
0x1400111f7  pop     rsi
0x1400111f8  pop     rbp
0x1400111f9  retn
```
