# CSessionThread::QueueWorkItem(void (*)(void *),void *)

- ea: `0x180028d00`
- end: `0x180028e64`
- name: `?QueueWorkItem@CSessionThread@@QEAAJP6AXPEAX@Z0@Z`
- size: `356`
- prototype: `__int64 __fastcall(CSessionThread *__hidden this, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800289dc`

## callees

- `0x180007da0`
- `0x18000b3d0`
- `0x18000b8f8`
- `0x18000b98c`
- `0x18000bd04`
- `0x18000bd44`
- `0x18001ba64`
- `0x180028d00`
- `0x180028fb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180028e3f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180028e3f`

## string_xrefs

- `0x180028df1`: `CSessionThread::QueueWorkItem ThreadInitialize failed`

## pseudocode

```c
__int64 __fastcall CSessionThread::QueueWorkItem(CSessionThread *this, void (*a2)(void *), __int64 a3)
{
  __int64 *v6; // rax
  __int64 *v7; // r14
  int v8; // eax
  int v9; // edi
  __int64 *v10; // rsi
  __int64 **v11; // rax
  int CurrentThreadActivityIdPrefix; // eax
  __int64 v13; // rcx
  __int64 *v14; // rax
  char *v16; // [rsp+50h] [rbp+8h] BYREF

  v16 = (char *)this + 72;
  CTSCriticalSection::Lock((CSessionThread *)((char *)this + 72));
  v6 = (__int64 *)operator new(0x20u);
  v7 = v6;
  if ( v6 )
  {
    v6[1] = a3;
    *v6 = (__int64)a2;
    v10 = v6 + 2;
    v11 = (__int64 **)*((_QWORD *)this + 8);
    v9 = 0;
    *v10 = (__int64)this + 56;
    v10[1] = (__int64)v11;
    *v11 = v10;
    ++*((_DWORD *)this + 12);
    *((_QWORD *)this + 8) = v10;
    if ( *((_QWORD *)this + 12) || (v9 = CSessionThread::ThreadInitialize(this), v9 >= 0) )
    {
      SetEvent(*((HANDLE *)this + 13));
    }
    else
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          21,
          (unsigned int)WPP_604055c0e96c35d1a7ac155e9fdb8c99_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"CSessionThread::QueueWorkItem ThreadInitialize failed",
          v9);
      }
      --*((_DWORD *)this + 12);
      v13 = *v10;
      v14 = (__int64 *)v10[1];
      *v14 = *v10;
      *(_QWORD *)(v13 + 8) = v14;
      operator delete(v7);
    }
  }
  else
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        20,
        (unsigned int)WPP_604055c0e96c35d1a7ac155e9fdb8c99_Traceguids,
        v8,
        (__int64)"PWORK_DETAILS");
    }
    v9 = -2147024882;
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180028d00  mov     [rsp+arg_8], rbx
0x180028d05  mov     [rsp+arg_10], rbp
0x180028d0a  push    rsi
0x180028d0b  push    rdi
0x180028d0c  push    r14
0x180028d0e  sub     rsp, 30h
0x180028d12  mov     rbx, rcx
0x180028d15  mov     rsi, r8
0x180028d18  add     rcx, 48h ; 'H'; this
0x180028d1c  mov     rbp, rdx
0x180028d1f  mov     [rsp+48h+arg_0], rcx
0x180028d24  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180028d29  mov     ecx, 20h ; ' '; Size
0x180028d2e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028d33  mov     r14, rax
0x180028d36  test    rax, rax
0x180028d39  jnz     short loc_180028D93
0x180028d3b  mov     rax, cs:WPP_GLOBAL_Control
0x180028d42  lea     rcx, WPP_GLOBAL_Control
0x180028d49  cmp     rax, rcx
0x180028d4c  jz      short loc_180028D89
0x180028d4e  test    byte ptr [rax+1Ch], 8
0x180028d52  jz      short loc_180028D89
0x180028d54  cmp     byte ptr [rax+19h], 2
0x180028d58  jb      short loc_180028D89
0x180028d5a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180028d5f  lea     rcx, aPworkDetails; "PWORK_DETAILS"
0x180028d66  mov     r9d, eax
0x180028d69  mov     [rsp+48h+var_28], rcx
0x180028d6e  lea     edx, [r14+14h]
0x180028d72  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d79  lea     r8, WPP_604055c0e96c35d1a7ac155e9fdb8c99_Traceguids
0x180028d80  mov     rcx, [rcx+10h]
0x180028d84  call    WPP_SF_Ds
0x180028d89  mov     edi, 8007000Eh
0x180028d8e  jmp     loc_180028E45
0x180028d93  mov     [rax+8], rsi
0x180028d97  lea     rcx, [rbx+38h]
0x180028d9b  mov     [rax], rbp
0x180028d9e  lea     rsi, [rax+10h]
0x180028da2  mov     rax, [rcx+8]
0x180028da6  xor     edi, edi
0x180028da8  mov     [rsi], rcx
0x180028dab  mov     [rsi+8], rax
0x180028daf  mov     [rax], rsi
0x180028db2  inc     dword ptr [rbx+30h]
0x180028db5  mov     [rcx+8], rsi
0x180028db9  cmp     [rbx+60h], rdi
0x180028dbd  jnz     short loc_180028E3B
0x180028dbf  mov     rcx, rbx; this
0x180028dc2  call    ?ThreadInitialize@CSessionThread@@AEAAJXZ; CSessionThread::ThreadInitialize(void)
0x180028dc7  mov     edi, eax
0x180028dc9  test    eax, eax
0x180028dcb  jns     short loc_180028E3B
0x180028dcd  mov     rax, cs:WPP_GLOBAL_Control
0x180028dd4  lea     rcx, WPP_GLOBAL_Control
0x180028ddb  cmp     rax, rcx
0x180028dde  jz      short loc_180028E20
0x180028de0  test    byte ptr [rax+1Ch], 8
0x180028de4  jz      short loc_180028E20
0x180028de6  cmp     byte ptr [rax+19h], 2
0x180028dea  jb      short loc_180028E20
0x180028dec  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180028df1  lea     rcx, aCsessionthread_3; "CSessionThread::QueueWorkItem ThreadIni"...
0x180028df8  mov     [rsp+48h+var_20], edi
0x180028dfc  mov     [rsp+48h+var_28], rcx
0x180028e01  lea     r8, WPP_604055c0e96c35d1a7ac155e9fdb8c99_Traceguids
0x180028e08  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e0f  mov     edx, 15h
0x180028e14  mov     r9d, eax
0x180028e17  mov     rcx, [rcx+10h]
0x180028e1b  call    WPP_SF_DsD
0x180028e20  dec     dword ptr [rbx+30h]
0x180028e23  mov     rcx, [rsi]
0x180028e26  mov     rax, [rsi+8]
0x180028e2a  mov     [rax], rcx
0x180028e2d  mov     [rcx+8], rax
0x180028e31  mov     rcx, r14; Block
0x180028e34  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180028e39  jmp     short loc_180028E45
0x180028e3b  mov     rcx, [rbx+68h]; hEvent
0x180028e3f  call    cs:__imp_SetEvent
0x180028e45  lea     rcx, [rsp+48h+arg_0]; this
0x180028e4a  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180028e4f  mov     rbx, [rsp+48h+arg_8]
0x180028e54  mov     eax, edi
0x180028e56  mov     rbp, [rsp+48h+arg_10]
0x180028e5b  add     rsp, 30h
0x180028e5f  pop     r14
0x180028e61  pop     rdi
0x180028e62  pop     rsi
0x180028e63  retn
```
