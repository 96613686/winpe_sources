# PnPServices::CInterfaceNotifBase::Callback(PnPServices::CPnPInterfaceEvent *)

- ea: `0x180001a30`
- end: `0x180001b9e`
- name: `?Callback@CInterfaceNotifBase@PnPServices@@QEAAJPEAVCPnPInterfaceEvent@2@@Z`
- size: `366`
- prototype: `__int64 __fastcall(HDPA *this, struct PnPServices::CPnPInterfaceEvent *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800023b0`

## callees

- `0x180001a30`
- `0x180003570`
- `0x180015f50`
- `0x18001b404`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001ab7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001ab7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001ac8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001ac8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001a5b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001a5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001b29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001b29`

## pseudocode

```c
__int64 __fastcall PnPServices::CInterfaceNotifBase::Callback(HDPA *this, struct PnPServices::CPnPInterfaceEvent *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r12
  _DWORD *v5; // rax
  _DWORD *v6; // rdi
  __int64 v7; // rsi
  int v8; // ebx
  HANDLE ProcessHeap; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rbp
  unsigned int v12; // ebx
  volatile signed __int32 **v13; // r14
  volatile signed __int32 *Ptr; // rax
  unsigned int v15; // ebp
  __int64 i; // rsi
  __int64 v17; // rax
  CRefCounted *v18; // r14

  v4 = (struct _RTL_CRITICAL_SECTION *)((unsigned __int64)(this + 4) & -(__int64)(this + 3 != 0));
  EnterCriticalSection(v4);
  v5 = operator new(0x20u);
  v6 = v5;
  if ( v5 )
  {
    v5[2] = 1;
    *(_QWORD *)v5 = &CGrowableArrayEnum<Storage::IDiskEventCB>::`vftable';
    v5[4] = 0;
    *((_QWORD *)v5 + 3) = 0;
    v7 = *(unsigned int *)this[2];
    if ( !(_DWORD)v7 )
    {
      *((_QWORD *)v5 + 3) = 0;
      v5[4] = 0;
LABEL_4:
      v8 = 0;
      goto LABEL_12;
    }
    ProcessHeap = GetProcessHeap();
    v10 = HeapAlloc(ProcessHeap, 8u, 8 * v7);
    v11 = v10;
    if ( v10 )
    {
      v12 = 0;
      v13 = (volatile signed __int32 **)v10;
      do
      {
        Ptr = (volatile signed __int32 *)g_pfn_DPA_GetPtr(this[2], v12);
        *v13 = Ptr;
        _InterlockedIncrement(Ptr + 2);
        ++v12;
        ++v13;
      }
      while ( v12 < (unsigned int)v7 );
      *((_QWORD *)v6 + 3) = v11;
      v6[4] = v7;
      goto LABEL_4;
    }
    v8 = -2147024882;
    (**(void (__fastcall ***)(_DWORD *, __int64))v6)(v6, 1);
  }
  else
  {
    v8 = -2147024882;
  }
  v6 = 0;
LABEL_12:
  LeaveCriticalSection(v4);
  if ( v8 >= 0 )
  {
    v15 = v6[4];
    for ( i = 0; (unsigned int)i < v15; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i < v6[4]
        && (_InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*((_QWORD *)v6 + 3) + 8 * i) + 8LL)),
            v17 = *((_QWORD *)v6 + 3),
            (v18 = *(CRefCounted **)(v17 + 8 * i)) != 0) )
      {
        v8 = 0;
        (*(void (__fastcall **)(_QWORD, struct PnPServices::CPnPInterfaceEvent *))(*(_QWORD *)v18 + 8LL))(
          *(_QWORD *)(v17 + 8 * i),
          a2);
        CRefCounted::Release(v18);
      }
      else
      {
        v8 = -2147467259;
      }
    }
    CRefCounted::Release((CRefCounted *)v6);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180001a30  push    rbx
0x180001a32  push    rbp
0x180001a33  push    rsi
0x180001a34  push    rdi
0x180001a35  push    r12
0x180001a37  push    r13
0x180001a39  push    r14
0x180001a3b  push    r15
0x180001a3d  sub     rsp, 28h
0x180001a41  lea     rax, [rcx+18h]
0x180001a45  mov     r15, rcx
0x180001a48  lea     r8, [rax+8]
0x180001a4c  mov     r13, rdx
0x180001a4f  neg     rax
0x180001a52  sbb     r12, r12
0x180001a55  and     r12, r8
0x180001a58  mov     rcx, r12; lpCriticalSection
0x180001a5b  call    cs:__imp_EnterCriticalSection
0x180001a61  mov     ecx, 20h ; ' '; Size
0x180001a66  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001a6b  mov     rdi, rax
0x180001a6e  test    rax, rax
0x180001a71  jz      loc_180001B1F
0x180001a77  mov     dword ptr [rax+8], 1
0x180001a7e  lea     rax, ??_7?$CGrowableArrayEnum@VIDiskEventCB@Storage@@@@6B@; const CGrowableArrayEnum<Storage::IDiskEventCB>::`vftable'
0x180001a85  mov     [rdi], rax
0x180001a88  mov     dword ptr [rdi+10h], 0
0x180001a8f  mov     qword ptr [rdi+18h], 0
0x180001a97  mov     rax, [r15+10h]
0x180001a9b  mov     esi, [rax]
0x180001a9d  test    esi, esi
0x180001a9f  jnz     short loc_180001AB0
0x180001aa1  mov     qword ptr [rdi+18h], 0
0x180001aa9  mov     [rdi+10h], esi
0x180001aac  xor     ebx, ebx
0x180001aae  jmp     short loc_180001B26
0x180001ab0  mov     rbx, rsi
0x180001ab3  shl     rbx, 3
0x180001ab7  call    cs:__imp_GetProcessHeap
0x180001abd  mov     r8, rbx; dwBytes
0x180001ac0  mov     edx, 8; dwFlags
0x180001ac5  mov     rcx, rax; hHeap
0x180001ac8  call    cs:__imp_HeapAlloc
0x180001ace  mov     rbp, rax
0x180001ad1  test    rax, rax
0x180001ad4  jz      short loc_180001B05
0x180001ad6  xor     ebx, ebx
0x180001ad8  mov     r14, rax
0x180001adb  test    esi, esi
0x180001add  jz      short loc_180001AFC
0x180001adf  mov     rcx, [r15+10h]; hdpa
0x180001ae3  mov     edx, ebx; i
0x180001ae5  call    cs:g_pfn_DPA_GetPtr
0x180001aeb  mov     [r14], rax
0x180001aee  lock inc dword ptr [rax+8]
0x180001af2  inc     ebx
0x180001af4  lea     r14, [r14+8]
0x180001af8  cmp     ebx, esi
0x180001afa  jb      short loc_180001ADF
0x180001afc  mov     [rdi+18h], rbp
0x180001b00  mov     [rdi+10h], esi
0x180001b03  jmp     short loc_180001AAC
0x180001b05  mov     rax, [rdi]
0x180001b08  mov     edx, 1
0x180001b0d  mov     rcx, rdi
0x180001b10  mov     ebx, 8007000Eh
0x180001b15  mov     rax, [rax]
0x180001b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b1d  jmp     short loc_180001B24
0x180001b1f  mov     ebx, 8007000Eh
0x180001b24  xor     edi, edi
0x180001b26  mov     rcx, r12; lpCriticalSection
0x180001b29  call    cs:__imp_LeaveCriticalSection
0x180001b2f  test    ebx, ebx
0x180001b31  js      short loc_180001B8B
0x180001b33  mov     ebp, [rdi+10h]
0x180001b36  xor     esi, esi
0x180001b38  test    ebp, ebp
0x180001b3a  jz      short loc_180001B83
0x180001b3c  cmp     esi, [rdi+10h]
0x180001b3f  jnb     short loc_180001B78
0x180001b41  mov     rax, [rdi+18h]
0x180001b45  mov     rcx, [rax+rsi*8]
0x180001b49  lock inc dword ptr [rcx+8]
0x180001b4d  mov     rax, [rdi+18h]
0x180001b51  mov     r14, [rax+rsi*8]
0x180001b55  test    r14, r14
0x180001b58  jz      short loc_180001B78
0x180001b5a  mov     rax, [r14]
0x180001b5d  mov     rdx, r13
0x180001b60  mov     rcx, r14
0x180001b63  xor     ebx, ebx
0x180001b65  mov     rax, [rax+8]
0x180001b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b6e  mov     rcx, r14; this
0x180001b71  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180001b76  jmp     short loc_180001B7D
0x180001b78  mov     ebx, 80004005h
0x180001b7d  inc     esi
0x180001b7f  cmp     esi, ebp
0x180001b81  jb      short loc_180001B3C
0x180001b83  mov     rcx, rdi; this
0x180001b86  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180001b8b  mov     eax, ebx
0x180001b8d  add     rsp, 28h
0x180001b91  pop     r15
0x180001b93  pop     r14
0x180001b95  pop     r13
0x180001b97  pop     r12
0x180001b99  pop     rdi
0x180001b9a  pop     rsi
0x180001b9b  pop     rbp
0x180001b9c  pop     rbx
0x180001b9d  retn
```
