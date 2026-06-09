# SNI_MemRegions::Init(void)

- ea: `0x10041e5b0`
- end: `0x10041e790`
- name: `?Init@SNI_MemRegions@@SAPEAV1@XZ`
- size: `480`
- prototype: `struct SNI_MemRegions *(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x100424110`

## callees

- `0x10041da80`
- `0x10041e4d0`
- `0x10041e5b0`
- `0x10041e7a0`
- `0x100486bf0`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10041e636`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10041e70f`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10041e636`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10041e70f`
- `sqldk!SystemThread_TlsIndex` at `0x10041e5d2`
- `sqldk!SystemThread_TlsIndex` at `0x10041e6ab`
- `sqldk!SystemThread_TlsOffset` at `0x10041e5db`
- `sqldk!SystemThread_TlsOffset` at `0x10041e6b4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041e5f6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041e6cf`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041e5f6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041e6cf`

## string_xrefs

- `0x10041e624`: `sql\common\dk\sni\include\SNI_MemRegion.hpp`
- `0x10041e6fd`: `sql\common\dk\sni\include\SNI_MemRegion.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
SNI_MemRegionProvider **SNI_MemRegions::Init(void)
{
  __int64 v0; // rbx
  __int64 v1; // rax
  _QWORD *v2; // rax
  SNI_MemRegionProvider **v3; // rbx
  _QWORD *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rsi
  __int64 v7; // rax
  void *v8; // rsi
  _QWORD v10[6]; // [rsp+38h] [rbp-30h] BYREF

  v0 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v1 = *(_QWORD *)(v0 + 256);
  if ( !v1 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v1 = *(_QWORD *)(v0 + 256);
  }
  v2 = operator new(
         0x88u,
         *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v1 + 992) + 56LL) + 8LL),
         1,
         "sql\\common\\dk\\sni\\include\\SNI_MemRegion.hpp",
         631,
         6u);
  v3 = (SNI_MemRegionProvider **)v2;
  if ( v2 )
  {
    *v2 = 0;
    v4 = v2 + 1;
    v5 = 16;
    do
    {
      *v4++ = 0;
      --v5;
    }
    while ( v5 );
  }
  else
  {
    v3 = 0;
  }
  if ( v3 && !(unsigned int)CCriticalSectionSOS::Initialize(v3) )
  {
    memset(v10, 0, 24);
    v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v7 = *(_QWORD *)(v6 + 256);
    if ( !v7 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v7 = *(_QWORD *)(v6 + 256);
    }
    v8 = operator new(
           0x180u,
           *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v7 + 992) + 56LL) + 8LL),
           1,
           "sql\\common\\dk\\sni\\include\\SNI_MemRegion.hpp",
           640,
           6u);
    if ( v8 )
      `eh vector constructor iterator'(
        v8,
        0x30u,
        8u,
        (void (*)(void *))SNI_MemRegion::SNI_MemRegion,
        (void (*)(void *))SNI_MemRegion::~SNI_MemRegion);
    else
      v8 = 0;
    v3[1] = (SNI_MemRegionProvider *)v8;
    if ( v3[1] && SNI_MemRegionProvider::FInit(v3[1], (const struct SNI_MemRegionProviderCallbacks *)v10) )
      return v3;
    SNI_MemRegions::`scalar deleting destructor'((SNI_MemRegions *)v3, 1u);
  }
  return 0;
}

```

## disassembly

```asm
0x10041e5b0  push    rbx
0x10041e5b2  push    rsi
0x10041e5b3  push    rdi
0x10041e5b4  sub     rsp, 50h
0x10041e5b8  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x10041e5c1  mov     [rsp+68h+arg_0], 277h
0x10041e5c9  mov     rdx, gs:58h
0x10041e5d2  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041e5d9  mov     ecx, [rax]
0x10041e5db  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041e5e2  mov     ebx, [rax]
0x10041e5e4  add     rbx, [rdx+rcx*8]
0x10041e5e8  mov     rax, [rbx+100h]
0x10041e5ef  test    rax, rax
0x10041e5f2  jnz     short loc_10041E603
0x10041e5f4  xor     ecx, ecx
0x10041e5f6  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041e5fc  mov     rax, [rbx+100h]
0x10041e603  mov     rax, [rax+3E0h]
0x10041e60a  mov     rcx, [rax+38h]
0x10041e60e  mov     rdx, [rcx+8]
0x10041e612  mov     [rsp+68h+arg_8], rdx
0x10041e617  mov     [rsp+68h+var_40], 6
0x10041e61c  mov     dword ptr [rsp+68h+var_48], 277h
0x10041e624  lea     r9, aSqlCommonDkSni_17; "sql\\common\\dk\\sni\\include\\SNI_MemR"...
0x10041e62b  mov     ecx, 88h
0x10041e630  mov     r8d, 1
0x10041e636  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10041e63c  mov     rbx, rax
0x10041e63f  mov     [rsp+68h+arg_10], rax
0x10041e647  xor     edi, edi
0x10041e649  test    rax, rax
0x10041e64c  jz      short loc_10041E66F
0x10041e64e  mov     [rax], rdi
0x10041e651  add     rax, 8
0x10041e655  mov     ecx, 10h
0x10041e65a  nop     word ptr [rax+rax+00h]
0x10041e660  mov     [rax], rdi
0x10041e663  lea     rax, [rax+8]
0x10041e667  sub     rcx, 1
0x10041e66b  jnz     short loc_10041E660
0x10041e66d  jmp     short loc_10041E672
0x10041e66f  mov     rbx, rdi
0x10041e672  test    rbx, rbx
0x10041e675  jz      loc_10041E786
0x10041e67b  mov     rcx, rbx; struct CCriticalSectionSOS **
0x10041e67e  call    ?Initialize@CCriticalSectionSOS@@SAKPEAPEAV1@@Z; CCriticalSectionSOS::Initialize(CCriticalSectionSOS * *)
0x10041e683  test    eax, eax
0x10041e685  jnz     loc_10041E786
0x10041e68b  mov     [rsp+68h+var_30], rdi
0x10041e690  mov     [rsp+68h+var_28], rdi
0x10041e695  mov     [rsp+68h+var_20], rdi
0x10041e69a  mov     [rsp+68h+arg_0], 280h
0x10041e6a2  mov     rdx, gs:58h
0x10041e6ab  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041e6b2  mov     ecx, [rax]
0x10041e6b4  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041e6bb  mov     esi, [rax]
0x10041e6bd  add     rsi, [rdx+rcx*8]
0x10041e6c1  mov     rax, [rsi+100h]
0x10041e6c8  test    rax, rax
0x10041e6cb  jnz     short loc_10041E6DC
0x10041e6cd  xor     ecx, ecx
0x10041e6cf  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041e6d5  mov     rax, [rsi+100h]
0x10041e6dc  mov     rax, [rax+3E0h]
0x10041e6e3  mov     rcx, [rax+38h]
0x10041e6e7  mov     rdx, [rcx+8]
0x10041e6eb  mov     [rsp+68h+arg_8], rdx
0x10041e6f0  mov     [rsp+68h+var_40], 6
0x10041e6f5  mov     dword ptr [rsp+68h+var_48], 280h
0x10041e6fd  lea     r9, aSqlCommonDkSni_17; "sql\\common\\dk\\sni\\include\\SNI_MemR"...
0x10041e704  mov     ecx, 180h
0x10041e709  mov     r8d, 1
0x10041e70f  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10041e715  mov     rsi, rax
0x10041e718  mov     [rsp+68h+arg_10], rax
0x10041e720  test    rax, rax
0x10041e723  jz      short loc_10041E74C
0x10041e725  lea     rax, ??1SNI_MemRegion@@QEAA@XZ; SNI_MemRegion::~SNI_MemRegion(void)
0x10041e72c  mov     [rsp+68h+var_48], rax; void (*)(void *)
0x10041e731  lea     r9, ??0SNI_MemRegion@@QEAA@XZ; void (*)(void *)
0x10041e738  mov     edx, 30h ; '0'; unsigned __int64
0x10041e73d  lea     r8d, [rdx-28h]; unsigned __int64
0x10041e741  mov     rcx, rsi; void *
0x10041e744  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x10041e749  nop
0x10041e74a  jmp     short loc_10041E74F
0x10041e74c  mov     rsi, rdi
0x10041e74f  mov     [rbx+8], rsi
0x10041e753  mov     rcx, [rbx+8]
0x10041e757  test    rcx, rcx
0x10041e75a  jz      short loc_10041E779
0x10041e75c  lea     rdx, [rsp+68h+var_30]; struct SNI_MemRegionProviderCallbacks *
0x10041e761  mov     rcx, [rbx+8]; this
0x10041e765  call    ?FInit@SNI_MemRegionProvider@@QEAA_NAEBUSNI_MemRegionProviderCallbacks@@@Z; SNI_MemRegionProvider::FInit(SNI_MemRegionProviderCallbacks const &)
0x10041e76a  test    al, al
0x10041e76c  jz      short loc_10041E779
0x10041e76e  mov     rax, rbx
0x10041e771  add     rsp, 50h
0x10041e775  pop     rdi
0x10041e776  pop     rsi
0x10041e777  pop     rbx
0x10041e778  retn
0x10041e779  mov     edx, 1; unsigned int
0x10041e77e  mov     rcx, rbx; this
0x10041e781  call    ??_GSNI_MemRegions@@QEAAPEAXI@Z; SNI_MemRegions::`scalar deleting destructor'(uint)
0x10041e786  xor     eax, eax
0x10041e788  add     rsp, 50h
0x10041e78c  pop     rdi
0x10041e78d  pop     rsi
0x10041e78e  pop     rbx
0x10041e78f  retn
```
