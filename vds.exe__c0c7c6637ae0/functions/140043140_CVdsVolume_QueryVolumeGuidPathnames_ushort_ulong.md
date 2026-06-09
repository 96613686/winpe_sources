# CVdsVolume::QueryVolumeGuidPathnames(ushort * * *,ulong *)

- ea: `0x140043140`
- end: `0x1400432e3`
- name: `?QueryVolumeGuidPathnames@CVdsVolume@@UEAAJPEAPEAPEAGPEAK@Z`
- size: `419`
- prototype: `__int64 __fastcall(CVdsVolume *__hidden this, unsigned __int16 ***, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003710`
- `0x140004360`
- `0x1400427c4`
- `0x140043140`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004329c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004329c`
- `vdsutil!VdsTraceEx` at `0x1400431f6`
- `vdsutil!VdsTraceEx` at `0x14004325b`
- `vdsutil!VdsTraceEx` at `0x14004328d`
- `vdsutil!VdsTraceEx` at `0x1400431f6`
- `vdsutil!VdsTraceEx` at `0x14004325b`
- `vdsutil!VdsTraceEx` at `0x14004328d`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140043194`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140043194`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400432b8`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400432b8`
- `vdsutil!GetVolumeGuidPathnames` at `0x140043272`
- `vdsutil!GetVolumeGuidPathnames` at `0x140043272`

## string_xrefs

- `0x140043182`: `CVdsVolume::QueryVolumeGuidPathnames()`
- `0x1400431e7`: `CVdsVolume::QueryVolumeGuidPathnames, 1, hr= %lX`
- `0x14004321f`: `CVdsVolume::QueryVolumeGuidPathnames, 2, hr= %lX`
- `0x14004324c`: `CVdsVolume::QueryVolumeGuidPathnames, 2a, hr=%lX`
- `0x140043281`: `CVdsVolume::QueryVolumeGuidPathnames, 3, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsVolume::QueryVolumeGuidPathnames(CVdsVolume *this, unsigned __int16 ***a2, unsigned int *a3)
{
  signed int v6; // ebx
  int v7; // eax
  int IsPackOffline; // eax
  int VolumeGuidPathnames; // eax
  __int64 v11; // [rsp+20h] [rbp-60h] BYREF
  int v12; // [rsp+28h] [rbp-58h]
  _BYTE v13[16]; // [rsp+30h] [rbp-50h] BYREF
  __int128 v14; // [rsp+40h] [rbp-40h] BYREF
  __int128 v15; // [rsp+50h] [rbp-30h]
  __int128 v16; // [rsp+60h] [rbp-20h]
  LPVOID pv; // [rsp+70h] [rbp-10h]

  v14 = 0;
  v15 = 0;
  v16 = 0;
  pv = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v13, 0x5Eu, "CVdsVolume::QueryVolumeGuidPathnames()");
  v14 = 0;
  v15 = 0;
  v16 = 0;
  pv = 0;
  v11 = 0;
  v12 = 0;
  v6 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v11);
  if ( v6 >= 0 )
  {
    *a3 = 0;
    *a2 = 0;
    if ( *((_QWORD *)this + 11) )
    {
      v7 = (*(__int64 (__fastcall **)(char *, __int128 *))(*((_QWORD *)this - 5) + 24LL))((char *)this - 40, &v14);
      v6 = v7;
      if ( v7 >= 0 )
      {
        if ( pv )
        {
          VolumeGuidPathnames = GetVolumeGuidPathnames((char *)pv + 28, a3, a2);
          v6 = VolumeGuidPathnames;
          if ( VolumeGuidPathnames < 0 )
            VdsTraceEx(94, 0, "CVdsVolume::QueryVolumeGuidPathnames, 3, hr=%lX", VolumeGuidPathnames);
        }
        else
        {
          IsPackOffline = CVdsVolume::IsPackOffline((CVdsVolume *)((char *)this - 40));
          v6 = IsPackOffline;
          if ( IsPackOffline >= 0 )
          {
            if ( IsPackOffline )
            {
              VdsTraceEx(94, 1, "CVdsVolume::QueryVolumeGuidPathnames, 2a, hr=%lX", IsPackOffline);
              v6 = -2147212223;
            }
            else
            {
              v6 = -2147212220;
            }
          }
        }
      }
      else
      {
        VdsTraceEx(94, 1, "CVdsVolume::QueryVolumeGuidPathnames, 2, hr= %lX", (unsigned int)v7);
      }
    }
    else
    {
      v6 = -2147212216;
      VdsTraceEx(94, 1, "CVdsVolume::QueryVolumeGuidPathnames, 1, hr= %lX", 2147755080LL);
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
  }
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v11);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140043140  mov     [rsp-28h+arg_18], rbx
0x140043145  push    rbp
0x140043146  push    rsi
0x140043147  push    rdi
0x140043148  push    r12
0x14004314a  push    r14
0x14004314c  mov     rbp, rsp
0x14004314f  sub     rsp, 80h
0x140043156  mov     rax, cs:__security_cookie
0x14004315d  xor     rax, rsp
0x140043160  mov     [rbp+var_8], rax
0x140043164  mov     r14, r8
0x140043167  mov     rsi, rdx
0x14004316a  mov     rdi, rcx
0x14004316d  xorps   xmm0, xmm0
0x140043170  xor     eax, eax
0x140043172  movups  [rbp+var_40], xmm0
0x140043176  movups  [rbp+var_30], xmm0
0x14004317a  movups  [rbp+var_20], xmm0
0x14004317e  mov     [rbp+pv], rax
0x140043182  lea     r8, aCvdsvolumeQuer_5; "CVdsVolume::QueryVolumeGuidPathnames()"
0x140043189  lea     r12d, [rax+5Eh]
0x14004318d  mov     edx, r12d
0x140043190  lea     rcx, [rbp+var_50]
0x140043194  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14004319a  nop
0x14004319b  xorps   xmm0, xmm0
0x14004319e  xor     eax, eax
0x1400431a0  movups  [rbp+var_40], xmm0
0x1400431a4  movups  [rbp+var_30], xmm0
0x1400431a8  movups  [rbp+var_20], xmm0
0x1400431ac  mov     [rbp+pv], rax
0x1400431b0  mov     [rbp+var_60], rax
0x1400431b4  mov     [rbp+var_58], eax
0x1400431b7  lea     rcx, [rbp+var_60]; this
0x1400431bb  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x1400431c0  mov     ebx, eax
0x1400431c2  test    eax, eax
0x1400431c4  js      loc_1400432AA
0x1400431ca  mov     dword ptr [r14], 0
0x1400431d1  mov     qword ptr [rsi], 0
0x1400431d8  cmp     qword ptr [rdi+58h], 0
0x1400431dd  jnz     short loc_140043201
0x1400431df  mov     ebx, 80042448h
0x1400431e4  mov     r9d, ebx
0x1400431e7  lea     r8, aCvdsvolumeQuer_6; "CVdsVolume::QueryVolumeGuidPathnames, 1"...
0x1400431ee  mov     edx, 1
0x1400431f3  mov     ecx, r12d
0x1400431f6  call    cs:__imp_VdsTraceEx
0x1400431fc  jmp     loc_140043293
0x140043201  mov     rax, [rdi-28h]
0x140043205  lea     rdx, [rbp+var_40]
0x140043209  lea     rcx, [rdi-28h]
0x14004320d  mov     rax, [rax+18h]
0x140043211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043216  mov     ebx, eax
0x140043218  test    eax, eax
0x14004321a  jns     short loc_140043228
0x14004321c  mov     r9d, eax
0x14004321f  lea     r8, aCvdsvolumeQuer_39; "CVdsVolume::QueryVolumeGuidPathnames, 2"...
0x140043226  jmp     short loc_1400431EE
0x140043228  mov     rcx, [rbp+pv]
0x14004322c  test    rcx, rcx
0x14004322f  jnz     short loc_140043268
0x140043231  lea     rcx, [rdi-28h]; this
0x140043235  call    ?IsPackOffline@CVdsVolume@@AEAAJXZ; CVdsVolume::IsPackOffline(void)
0x14004323a  mov     ebx, eax
0x14004323c  test    eax, eax
0x14004323e  js      short loc_140043293
0x140043240  jnz     short loc_140043249
0x140043242  mov     ebx, 80042444h
0x140043247  jmp     short loc_140043293
0x140043249  mov     r9d, eax
0x14004324c  lea     r8, aCvdsvolumeQuer_31; "CVdsVolume::QueryVolumeGuidPathnames, 2"...
0x140043253  mov     edx, 1
0x140043258  mov     ecx, r12d
0x14004325b  call    cs:__imp_VdsTraceEx
0x140043261  mov     ebx, 80042441h
0x140043266  jmp     short loc_140043293
0x140043268  add     rcx, 1Ch
0x14004326c  mov     r8, rsi
0x14004326f  mov     rdx, r14
0x140043272  call    cs:__imp_GetVolumeGuidPathnames
0x140043278  mov     ebx, eax
0x14004327a  test    eax, eax
0x14004327c  jns     short loc_140043293
0x14004327e  mov     r9d, eax
0x140043281  lea     r8, aCvdsvolumeQuer_0; "CVdsVolume::QueryVolumeGuidPathnames, 3"...
0x140043288  xor     edx, edx
0x14004328a  mov     ecx, r12d
0x14004328d  call    cs:__imp_VdsTraceEx
0x140043293  mov     rcx, [rbp+pv]; pv
0x140043297  test    rcx, rcx
0x14004329a  jz      short loc_1400432AA
0x14004329c  call    cs:__imp_CoTaskMemFree
0x1400432a2  mov     [rbp+pv], 0
0x1400432aa  lea     rcx, [rbp+var_60]; this
0x1400432ae  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x1400432b3  nop
0x1400432b4  lea     rcx, [rbp+var_50]
0x1400432b8  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400432be  mov     eax, ebx
0x1400432c0  mov     rcx, [rbp+var_8]
0x1400432c4  xor     rcx, rsp; StackCookie
0x1400432c7  call    __security_check_cookie
0x1400432cc  mov     rbx, [rsp+80h+arg_18]
0x1400432d4  add     rsp, 80h
0x1400432db  pop     r14
0x1400432dd  pop     r12
0x1400432df  pop     rdi
0x1400432e0  pop     rsi
0x1400432e1  pop     rbp
0x1400432e2  retn
```
