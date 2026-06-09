# CWsmTrackingConfig::CTrackingConfig::RemoveTrackedStablePath(ushort const *)

- ea: `0x14000b77c`
- end: `0x14000b95c`
- name: `?RemoveTrackedStablePath@CTrackingConfig@CWsmTrackingConfig@@QEAAJPEBG@Z`
- size: `480`
- prototype: `int(CWsmTrackingConfig::CTrackingConfig *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000b550`
- `0x14000b970`

## callees

- `0x1400088ec`
- `0x1400091cc`
- `0x14000b77c`
- `0x14000c1d8`
- `0x14000d0a8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b817`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b84c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b8ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b817`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b84c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b8ad`
- `ntoskrnl!_wcsicmp` at `0x14000b7b7`
- `ntoskrnl!_wcsicmp` at `0x14000b7b7`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::CTrackingConfig::RemoveTrackedStablePath(
        CWsmTrackingConfig::CTrackingConfig *this,
        const unsigned __int16 *a2)
{
  char v2; // si
  __int64 v3; // rbp
  __int64 v6; // rcx
  PVOID *v7; // rbx
  __int64 v8; // rsi
  __int64 v9; // r12
  __int64 v10; // r14
  __int64 v11; // rax
  void ***v12; // r15
  void ****v13; // rax
  void ***v14; // rsi
  __int64 v15; // rdx
  PVOID v16; // rax
  __int64 *v17; // rsi
  __int64 v19; // r8
  unsigned __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rax
  __int128 v23; // xmm0
  __int64 v24; // xmm1_8
  __int64 v25; // rcx

  v2 = 0;
  v3 = 0;
  if ( *((_DWORD *)this + 26) )
  {
    do
    {
      v7 = (PVOID *)((char *)this + 8);
      if ( !_wcsicmp(*(const wchar_t **)(*((_QWORD *)this + 14) + 24 * v3), a2) )
      {
        v8 = 0;
        v9 = (__int64)*v7 + 8 * v3;
        v10 = (*((_QWORD *)this + 2) - v9 - 8) >> 3;
        if ( v10 )
        {
          do
          {
            v11 = *(_QWORD *)(v9 + 8 * v8 + 8);
            *(_QWORD *)(v9 + 8 * v8 + 8) = 0;
            v12 = *(void ****)(v9 + 8 * v8);
            *(_QWORD *)(v9 + 8 * v8) = v11;
            if ( v12 )
            {
              CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(v12);
              ExFreePoolWithTag(v12, 0x6E6D7377u);
            }
            ++v8;
          }
          while ( v8 != v10 );
        }
        *((_QWORD *)this + 2) -= 8LL;
        v13 = (void ****)*((_QWORD *)this + 2);
        v14 = *v13;
        if ( *v13 )
        {
          CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(*v13);
          ExFreePoolWithTag(v14, 0x6E6D7377u);
        }
        v2 = 1;
      }
      v3 = (unsigned int)(v3 + 1);
    }
    while ( (unsigned int)v3 < *((_DWORD *)this + 26) );
    if ( v2 )
    {
      v15 = *((_QWORD *)this + 2);
      if ( v15 != *((_QWORD *)this + 3) )
      {
        v16 = *v7;
        if ( (v15 - (__int64)*v7) >> 3 )
        {
          if ( !(unsigned __int8)utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>::_SetCapacity((char *)this + 8) )
            return 3221225626LL;
        }
        else
        {
          if ( v16 != (PVOID)-1LL )
          {
            *((_QWORD *)this + 2) = v16;
            utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>(
              v6,
              v16,
              0);
            if ( *v7 )
              ExFreePoolWithTag(*v7, 0x6E6D7377u);
          }
          *v7 = (PVOID)-1LL;
          *((_QWORD *)this + 2) = -1;
          *((_QWORD *)this + 3) = -1;
        }
      }
      v17 = (__int64 *)((char *)this + 32);
      if ( !utl::vector<_WSM_TRACKING_PATH_INFO,utl::allocator<_WSM_TRACKING_PATH_INFO>>::resize(
              (__int64 *)this + 4,
              (__int64)(*((_QWORD *)this + 2) - *((_QWORD *)this + 1)) >> 3) )
        return 3221225626LL;
      v19 = 0;
      v20 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 5) - *((_QWORD *)this + 4)) >> 3);
      *((_DWORD *)this + 26) = v20;
      if ( (_DWORD)v20 )
      {
        do
        {
          v21 = *((_QWORD *)*v7 + v19);
          v22 = *v17;
          v23 = *(_OWORD *)(v21 + 72);
          v24 = *(_QWORD *)(v21 + 88);
          v25 = 3 * v19;
          *(_OWORD *)(v22 + 8 * v25) = v23;
          v19 = (unsigned int)(v19 + 1);
          *(_QWORD *)(v22 + 8 * v25 + 16) = v24;
        }
        while ( (unsigned int)v19 < *((_DWORD *)this + 26) );
      }
      *((_QWORD *)this + 14) = *v17;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000b77c  push    rbx
0x14000b77e  push    rbp
0x14000b77f  push    rsi
0x14000b780  push    rdi
0x14000b781  push    r12
0x14000b783  push    r13
0x14000b785  push    r14
0x14000b787  push    r15
0x14000b789  sub     rsp, 28h
0x14000b78d  xor     sil, sil
0x14000b790  xor     ebp, ebp
0x14000b792  mov     r13, rdx
0x14000b795  mov     rdi, rcx
0x14000b798  cmp     [rcx+68h], ebp
0x14000b79b  jbe     loc_14000B948
0x14000b7a1  mov     rcx, [rdi+70h]
0x14000b7a5  lea     rax, ds:0[rbp*2]
0x14000b7ad  add     rax, rbp
0x14000b7b0  mov     rdx, r13; Str2
0x14000b7b3  mov     rcx, [rcx+rax*8]; Str1
0x14000b7b7  call    cs:__imp__wcsicmp
0x14000b7be  nop     dword ptr [rax+rax+00h]
0x14000b7c3  lea     rbx, [rdi+8]
0x14000b7c7  test    eax, eax
0x14000b7c9  jnz     loc_14000B85B
0x14000b7cf  mov     rax, [rbx]
0x14000b7d2  xor     esi, esi
0x14000b7d4  mov     r14, [rbx+8]
0x14000b7d8  lea     r12, [rax+rbp*8]
0x14000b7dc  sub     r14, r12
0x14000b7df  sub     r14, 8
0x14000b7e3  sar     r14, 3
0x14000b7e7  test    r14, r14
0x14000b7ea  jz      short loc_14000B82B
0x14000b7ec  mov     rax, [r12+rsi*8+8]
0x14000b7f1  mov     qword ptr [r12+rsi*8+8], 0
0x14000b7fa  mov     r15, [r12+rsi*8]
0x14000b7fe  mov     [r12+rsi*8], rax
0x14000b802  test    r15, r15
0x14000b805  jz      short loc_14000B823
0x14000b807  mov     rcx, r15; this
0x14000b80a  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x14000b80f  mov     edx, 6E6D7377h; Tag
0x14000b814  mov     rcx, r15; P
0x14000b817  call    cs:__imp_ExFreePoolWithTag
0x14000b81e  nop     dword ptr [rax+rax+00h]
0x14000b823  inc     rsi
0x14000b826  cmp     rsi, r14
0x14000b829  jnz     short loc_14000B7EC
0x14000b82b  add     qword ptr [rbx+8], 0FFFFFFFFFFFFFFF8h
0x14000b830  mov     rax, [rbx+8]
0x14000b834  mov     rsi, [rax]
0x14000b837  test    rsi, rsi
0x14000b83a  jz      short loc_14000B858
0x14000b83c  mov     rcx, rsi; this
0x14000b83f  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x14000b844  mov     edx, 6E6D7377h; Tag
0x14000b849  mov     rcx, rsi; P
0x14000b84c  call    cs:__imp_ExFreePoolWithTag
0x14000b853  nop     dword ptr [rax+rax+00h]
0x14000b858  mov     sil, 1
0x14000b85b  inc     ebp
0x14000b85d  cmp     ebp, [rdi+68h]
0x14000b860  jb      loc_14000B7A1
0x14000b866  test    sil, sil
0x14000b869  jz      loc_14000B948
0x14000b86f  mov     rdx, [rbx+8]
0x14000b873  cmp     rdx, [rbx+10h]
0x14000b877  jz      short loc_14000B8D2
0x14000b879  mov     rax, [rbx]
0x14000b87c  sub     rdx, rax
0x14000b87f  sar     rdx, 3
0x14000b883  test    rdx, rdx
0x14000b886  jnz     short loc_14000B8C6
0x14000b888  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000b88c  cmp     rax, rsi
0x14000b88f  jz      short loc_14000B8B9
0x14000b891  mov     r8, rdx
0x14000b894  mov     [rbx+8], rax
0x14000b898  mov     rdx, rax
0x14000b89b  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@0@PEAV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>(utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>> &,utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>> *,unsigned __int64)
0x14000b8a0  mov     rcx, [rbx]; P
0x14000b8a3  test    rcx, rcx
0x14000b8a6  jz      short loc_14000B8B9
0x14000b8a8  mov     edx, 6E6D7377h; Tag
0x14000b8ad  call    cs:__imp_ExFreePoolWithTag
0x14000b8b4  nop     dword ptr [rax+rax+00h]
0x14000b8b9  mov     [rbx], rsi
0x14000b8bc  mov     [rbx+8], rsi
0x14000b8c0  mov     [rbx+10h], rsi
0x14000b8c4  jmp     short loc_14000B8D2
0x14000b8c6  mov     rcx, rbx
0x14000b8c9  call    ?_SetCapacity@?$vector@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>::_SetCapacity(unsigned __int64)
0x14000b8ce  test    al, al
0x14000b8d0  jz      short loc_14000B8ED
0x14000b8d2  mov     rdx, [rbx+8]
0x14000b8d6  lea     rsi, [rdi+20h]
0x14000b8da  sub     rdx, [rbx]
0x14000b8dd  mov     rcx, rsi
0x14000b8e0  sar     rdx, 3
0x14000b8e4  call    ?resize@?$vector@U_WSM_TRACKING_PATH_INFO@@V?$allocator@U_WSM_TRACKING_PATH_INFO@@@utl@@@utl@@QEAA_N_K@Z; utl::vector<_WSM_TRACKING_PATH_INFO,utl::allocator<_WSM_TRACKING_PATH_INFO>>::resize(unsigned __int64)
0x14000b8e9  test    al, al
0x14000b8eb  jnz     short loc_14000B8F4
0x14000b8ed  mov     eax, 0C000009Ah
0x14000b8f2  jmp     short loc_14000B94A
0x14000b8f4  mov     rcx, [rsi+8]
0x14000b8f8  mov     rax, 0AAAAAAAAAAAAAAABh
0x14000b902  sub     rcx, [rsi]
0x14000b905  xor     r8d, r8d
0x14000b908  sar     rcx, 3
0x14000b90c  imul    rcx, rax
0x14000b910  mov     [rdi+68h], ecx
0x14000b913  test    ecx, ecx
0x14000b915  jz      short loc_14000B941
0x14000b917  mov     rax, [rbx]
0x14000b91a  mov     rcx, [rax+r8*8]
0x14000b91e  mov     rax, [rsi]
0x14000b921  movups  xmm0, xmmword ptr [rcx+48h]
0x14000b925  movsd   xmm1, qword ptr [rcx+58h]
0x14000b92a  lea     rcx, [r8+r8*2]
0x14000b92e  movups  xmmword ptr [rax+rcx*8], xmm0
0x14000b932  inc     r8d
0x14000b935  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x14000b93b  cmp     r8d, [rdi+68h]
0x14000b93f  jb      short loc_14000B917
0x14000b941  mov     rax, [rsi]
0x14000b944  mov     [rdi+70h], rax
0x14000b948  xor     eax, eax
0x14000b94a  add     rsp, 28h
0x14000b94e  pop     r15
0x14000b950  pop     r14
0x14000b952  pop     r13
0x14000b954  pop     r12
0x14000b956  pop     rdi
0x14000b957  pop     rsi
0x14000b958  pop     rbp
0x14000b959  pop     rbx
0x14000b95a  retn
```
