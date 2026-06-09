# CWsmTrackingConfig::CTrackingConfig::deserialize(read_buffer_aligned &)

- ea: `0x14000c6f0`
- end: `0x14000c9a1`
- name: `?deserialize@CTrackingConfig@CWsmTrackingConfig@@UEAAJAEAVread_buffer_aligned@@@Z`
- size: `689`
- prototype: `__int64 __fastcall(CWsmTrackingConfig::CTrackingConfig *__hidden this, struct read_buffer_aligned *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x140008bb0`
- `0x140008c08`
- `0x1400091cc`
- `0x14000a8c4`
- `0x14000b280`
- `0x14000c6f0`
- `0x14000d0a8`
- `0x14000d21c`
- `0x14000f9e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c86d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c914`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c962`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c989`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c86d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c914`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c962`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c989`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::CTrackingConfig::deserialize(
        CWsmTrackingConfig::CTrackingConfig *this,
        struct read_buffer_aligned *a2)
{
  __int64 result; // rax
  _QWORD *v5; // rax
  __int64 v6; // rcx
  _QWORD *v7; // rax
  __int64 v8; // rcx
  int v9; // edi
  unsigned int v10; // eax
  __int64 *v11; // r13
  __int64 *v12; // r12
  __int64 v13; // r14
  struct CWsmTrackingConfig::CTrackingPathInfo **v14; // rax
  int Instance; // r15d
  CWsmTrackingConfig::CTrackingPathInfo *v16; // rdi
  __int64 v17; // rax
  PVOID v18; // rdx
  CWsmTrackingConfig::CTrackingPathInfo *v19; // rdi
  __int64 v20; // rcx
  __int64 v21; // rax
  __int128 v22; // xmm0
  __int64 v23; // xmm1_8
  __int64 v24; // rcx
  PVOID v25; // r15
  PVOID v26; // rbx
  PVOID v27; // rbx
  CWsmTrackingConfig::CTrackingPathInfo *v28; // [rsp+20h] [rbp-28h] BYREF
  CWsmTrackingConfig::CTrackingPathInfo **v29; // [rsp+28h] [rbp-20h]
  PVOID P; // [rsp+A0h] [rbp+58h] BYREF

  CWsmTrackingConfig::CTrackingConfig::Release(this);
  LODWORD(P) = 0;
  result = read_buffer_aligned::read<unsigned long>(a2, &P);
  if ( (int)result >= 0 )
  {
    if ( (_DWORD)P != 1852666743 )
      return 3221227289LL;
    LODWORD(P) = 0;
    result = read_buffer_aligned::read<unsigned long>(a2, &P);
    if ( (int)result >= 0 )
    {
      if ( (_DWORD)P != 6 )
        return 3221225561LL;
      result = (*(__int64 (__fastcall **)(char *, struct read_buffer_aligned *))(*((_QWORD *)this + 7) + 8LL))(
                 (char *)this + 56,
                 a2);
      if ( (int)result >= 0 )
      {
        v5 = (_QWORD *)*((_QWORD *)this + 8);
        v6 = v5 ? *v5 : 0LL;
        *((_QWORD *)this + 11) = v6;
        result = (*(__int64 (__fastcall **)(char *, struct read_buffer_aligned *))(*((_QWORD *)this + 9) + 8LL))(
                   (char *)this + 72,
                   a2);
        if ( (int)result >= 0 )
        {
          v7 = (_QWORD *)*((_QWORD *)this + 10);
          v8 = v7 ? *v7 : 0LL;
          *((_QWORD *)this + 12) = v8;
          result = read_buffer_aligned::read<unsigned long>(a2, (char *)this + 104);
          v9 = result;
          if ( (int)result >= 0 )
          {
            v10 = *((_DWORD *)this + 26);
            if ( v10 )
            {
              v11 = (__int64 *)((char *)this + 8);
              if ( !(unsigned __int8)utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>::resize(
                                       (char *)this + 8,
                                       v10) )
                return 3221225626LL;
              v12 = (__int64 *)((char *)this + 32);
              if ( !(unsigned __int8)utl::vector<_WSM_TRACKING_PATH_INFO,utl::allocator<_WSM_TRACKING_PATH_INFO>>::resize(
                                       (char *)this + 32,
                                       *((unsigned int *)this + 26)) )
                return 3221225626LL;
              v13 = 0;
              if ( *((_DWORD *)this + 26) )
              {
                while ( 1 )
                {
                  P = 0;
                  v14 = (struct CWsmTrackingConfig::CTrackingPathInfo **)utl::out_ptr<void,utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,>(
                                                                           &v28,
                                                                           &P);
                  Instance = CWsmTrackingConfig::CTrackingPathInfo::CreateInstance(0, 1, v14);
                  if ( v28 )
                  {
                    v16 = *v29;
                    *v29 = v28;
                    if ( v16 )
                    {
                      CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(v16);
                      ExFreePoolWithTag(v16, 0x6E6D7377u);
                    }
                  }
                  if ( Instance < 0 )
                    break;
                  v17 = *v11;
                  v18 = P;
                  P = 0;
                  v19 = *(CWsmTrackingConfig::CTrackingPathInfo **)(v17 + 8 * v13);
                  *(_QWORD *)(v17 + 8 * v13) = v18;
                  if ( v19 )
                  {
                    CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(v19);
                    ExFreePoolWithTag(v19, 0x6E6D7377u);
                  }
                  v9 = (*(__int64 (__fastcall **)(_QWORD, struct read_buffer_aligned *))(**(_QWORD **)(*v11 + 8 * v13)
                                                                                       + 8LL))(
                         *(_QWORD *)(*v11 + 8 * v13),
                         a2);
                  if ( v9 < 0 )
                  {
                    v26 = P;
                    if ( P )
                    {
                      CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo((CWsmTrackingConfig::CTrackingPathInfo *)P);
                      ExFreePoolWithTag(v26, 0x6E6D7377u);
                    }
                    return (unsigned int)v9;
                  }
                  v20 = *(_QWORD *)(*v11 + 8 * v13);
                  v21 = *v12;
                  v22 = *(_OWORD *)(v20 + 72);
                  v23 = *(_QWORD *)(v20 + 88);
                  v24 = 3 * v13;
                  *(_OWORD *)(v21 + 8 * v24) = v22;
                  *(_QWORD *)(v21 + 8 * v24 + 16) = v23;
                  v25 = P;
                  if ( P )
                  {
                    CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo((CWsmTrackingConfig::CTrackingPathInfo *)P);
                    ExFreePoolWithTag(v25, 0x6E6D7377u);
                  }
                  v13 = (unsigned int)(v13 + 1);
                  if ( (unsigned int)v13 >= *((_DWORD *)this + 26) )
                    goto LABEL_30;
                }
                v27 = P;
                if ( P )
                {
                  CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo((CWsmTrackingConfig::CTrackingPathInfo *)P);
                  ExFreePoolWithTag(v27, 0x6E6D7377u);
                }
                return (unsigned int)Instance;
              }
LABEL_30:
              *((_QWORD *)this + 14) = *v12;
            }
            return (unsigned int)v9;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000c6f0  push    rbp
0x14000c6f2  push    rbx
0x14000c6f3  push    rsi
0x14000c6f4  push    rdi
0x14000c6f5  push    r12
0x14000c6f7  push    r13
0x14000c6f9  push    r14
0x14000c6fb  push    r15
0x14000c6fd  mov     rbp, rsp
0x14000c700  sub     rsp, 48h
0x14000c704  mov     rsi, rdx
0x14000c707  mov     rbx, rcx
0x14000c70a  call    ?Release@CTrackingConfig@CWsmTrackingConfig@@IEAAXXZ; CWsmTrackingConfig::CTrackingConfig::Release(void)
0x14000c70f  lea     rdx, [rbp+P]
0x14000c713  mov     dword ptr [rbp+P], 0
0x14000c71a  mov     rcx, rsi
0x14000c71d  call    ??$read@K@read_buffer_aligned@@QEAAJAEAK@Z; read_buffer_aligned::read<ulong>(ulong &)
0x14000c722  test    eax, eax
0x14000c724  js      loc_14000C937
0x14000c72a  cmp     dword ptr [rbp+P], 6E6D7377h
0x14000c731  jz      short loc_14000C73D
0x14000c733  mov     eax, 0C0000719h
0x14000c738  jmp     loc_14000C937
0x14000c73d  lea     rdx, [rbp+P]
0x14000c741  mov     dword ptr [rbp+P], 0
0x14000c748  mov     rcx, rsi
0x14000c74b  call    ??$read@K@read_buffer_aligned@@QEAAJAEAK@Z; read_buffer_aligned::read<ulong>(ulong &)
0x14000c750  test    eax, eax
0x14000c752  js      loc_14000C937
0x14000c758  cmp     dword ptr [rbp+P], 6
0x14000c75c  jz      short loc_14000C768
0x14000c75e  mov     eax, 0C0000059h
0x14000c763  jmp     loc_14000C937
0x14000c768  lea     rcx, [rbx+38h]
0x14000c76c  mov     rdx, rsi
0x14000c76f  mov     rax, [rcx]
0x14000c772  mov     rax, [rax+8]
0x14000c776  call    _guard_dispatch_icall
0x14000c77b  test    eax, eax
0x14000c77d  js      loc_14000C937
0x14000c783  mov     rax, [rbx+40h]
0x14000c787  test    rax, rax
0x14000c78a  jz      short loc_14000C791
0x14000c78c  mov     rcx, [rax]
0x14000c78f  jmp     short loc_14000C793
0x14000c791  xor     ecx, ecx
0x14000c793  mov     [rbx+58h], rcx
0x14000c797  mov     rdx, rsi
0x14000c79a  lea     rcx, [rbx+48h]
0x14000c79e  mov     rax, [rcx]
0x14000c7a1  mov     rax, [rax+8]
0x14000c7a5  call    _guard_dispatch_icall
0x14000c7aa  test    eax, eax
0x14000c7ac  js      loc_14000C937
0x14000c7b2  mov     rax, [rbx+50h]
0x14000c7b6  test    rax, rax
0x14000c7b9  jz      short loc_14000C7C0
0x14000c7bb  mov     rcx, [rax]
0x14000c7be  jmp     short loc_14000C7C2
0x14000c7c0  xor     ecx, ecx
0x14000c7c2  mov     [rbx+60h], rcx
0x14000c7c6  lea     rdx, [rbx+68h]
0x14000c7ca  mov     rcx, rsi
0x14000c7cd  call    ??$read@K@read_buffer_aligned@@QEAAJAEAK@Z; read_buffer_aligned::read<ulong>(ulong &)
0x14000c7d2  mov     edi, eax
0x14000c7d4  test    eax, eax
0x14000c7d6  js      loc_14000C937
0x14000c7dc  mov     eax, [rbx+68h]
0x14000c7df  test    eax, eax
0x14000c7e1  jz      loc_14000C935
0x14000c7e7  lea     r13, [rbx+8]
0x14000c7eb  mov     edx, eax
0x14000c7ed  mov     rcx, r13
0x14000c7f0  call    ?resize@?$vector@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@2@@utl@@QEAA_N_K@Z; utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>::resize(unsigned __int64)
0x14000c7f5  test    al, al
0x14000c7f7  jz      loc_14000C99A
0x14000c7fd  mov     edx, [rbx+68h]
0x14000c800  lea     r12, [rbx+20h]
0x14000c804  mov     rcx, r12
0x14000c807  call    ?resize@?$vector@U_WSM_TRACKING_PATH_INFO@@V?$allocator@U_WSM_TRACKING_PATH_INFO@@@utl@@@utl@@QEAA_N_K@Z; utl::vector<_WSM_TRACKING_PATH_INFO,utl::allocator<_WSM_TRACKING_PATH_INFO>>::resize(unsigned __int64)
0x14000c80c  test    al, al
0x14000c80e  jz      loc_14000C99A
0x14000c814  xor     r14d, r14d
0x14000c817  cmp     [rbx+68h], r14d
0x14000c81b  jbe     loc_14000C92D
0x14000c821  lea     rdx, [rbp+P]
0x14000c825  mov     [rbp+P], 0
0x14000c82d  lea     rcx, [rbp+var_28]
0x14000c831  call    ??$out_ptr@XV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@0@@Z
0x14000c836  mov     r8, rax; struct CWsmTrackingConfig::CTrackingPathInfo **
0x14000c839  mov     dl, 1; bool
0x14000c83b  xor     ecx, ecx; struct _WSM_TRACKING_PATH_INFO *
0x14000c83d  call    ?CreateInstance@CTrackingPathInfo@CWsmTrackingConfig@@SAJQEAU_WSM_TRACKING_PATH_INFO@@_NPEAPEAV12@@Z; CWsmTrackingConfig::CTrackingPathInfo::CreateInstance(_WSM_TRACKING_PATH_INFO * const,bool,CWsmTrackingConfig::CTrackingPathInfo * *)
0x14000c842  mov     r15d, eax
0x14000c845  mov     rax, [rbp+var_28]
0x14000c849  test    rax, rax
0x14000c84c  jz      short loc_14000C879
0x14000c84e  mov     rdx, [rbp+var_20]
0x14000c852  mov     rdi, [rdx]
0x14000c855  mov     [rdx], rax
0x14000c858  test    rdi, rdi
0x14000c85b  jz      short loc_14000C879
0x14000c85d  mov     rcx, rdi; this
0x14000c860  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x14000c865  mov     edx, 6E6D7377h; Tag
0x14000c86a  mov     rcx, rdi; P
0x14000c86d  call    cs:__imp_ExFreePoolWithTag
0x14000c874  nop     dword ptr [rax+rax+00h]
0x14000c879  test    r15d, r15d
0x14000c87c  js      loc_14000C970
0x14000c882  mov     rax, [r13+0]
0x14000c886  mov     rdx, [rbp+P]
0x14000c88a  mov     [rbp+P], 0
0x14000c892  mov     rdi, [rax+r14*8]
0x14000c896  mov     [rax+r14*8], rdx
0x14000c89a  test    rdi, rdi
0x14000c89d  jz      short loc_14000C8BB
0x14000c89f  mov     rcx, rdi; this
0x14000c8a2  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x14000c8a7  mov     edx, 6E6D7377h; Tag
0x14000c8ac  mov     rcx, rdi; P
0x14000c8af  call    cs:__imp_ExFreePoolWithTag
0x14000c8b6  nop     dword ptr [rax+rax+00h]
0x14000c8bb  mov     rax, [r13+0]
0x14000c8bf  mov     rdx, rsi
0x14000c8c2  mov     rcx, [rax+r14*8]
0x14000c8c6  mov     rax, [rcx]
0x14000c8c9  mov     rax, [rax+8]
0x14000c8cd  call    _guard_dispatch_icall
0x14000c8d2  mov     edi, eax
0x14000c8d4  test    eax, eax
0x14000c8d6  js      short loc_14000C949
0x14000c8d8  mov     rax, [r13+0]
0x14000c8dc  mov     rcx, [rax+r14*8]
0x14000c8e0  mov     rax, [r12]
0x14000c8e4  movups  xmm0, xmmword ptr [rcx+48h]
0x14000c8e8  movsd   xmm1, qword ptr [rcx+58h]
0x14000c8ed  lea     rcx, [r14+r14*2]
0x14000c8f1  movups  xmmword ptr [rax+rcx*8], xmm0
0x14000c8f5  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x14000c8fb  mov     r15, [rbp+P]
0x14000c8ff  test    r15, r15
0x14000c902  jz      short loc_14000C920
0x14000c904  mov     rcx, r15; this
0x14000c907  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x14000c90c  mov     edx, 6E6D7377h; Tag
0x14000c911  mov     rcx, r15; P
0x14000c914  call    cs:__imp_ExFreePoolWithTag
0x14000c91b  nop     dword ptr [rax+rax+00h]
0x14000c920  inc     r14d
0x14000c923  cmp     r14d, [rbx+68h]
0x14000c927  jb      loc_14000C821
0x14000c92d  mov     rax, [r12]
0x14000c931  mov     [rbx+70h], rax
0x14000c935  mov     eax, edi
0x14000c937  add     rsp, 48h
0x14000c93b  pop     r15
0x14000c93d  pop     r14
0x14000c93f  pop     r13
0x14000c941  pop     r12
0x14000c943  pop     rdi
0x14000c944  pop     rsi
0x14000c945  pop     rbx
0x14000c946  pop     rbp
0x14000c947  retn
0x14000c949  mov     rbx, [rbp+P]
0x14000c94d  test    rbx, rbx
0x14000c950  jz      short loc_14000C935
0x14000c952  mov     rcx, rbx; this
0x14000c955  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x14000c95a  mov     edx, 6E6D7377h; Tag
0x14000c95f  mov     rcx, rbx; P
0x14000c962  call    cs:__imp_ExFreePoolWithTag
0x14000c969  nop     dword ptr [rax+rax+00h]
0x14000c96e  jmp     short loc_14000C935
0x14000c970  mov     rbx, [rbp+P]
0x14000c974  test    rbx, rbx
0x14000c977  jz      short loc_14000C995
0x14000c979  mov     rcx, rbx; this
0x14000c97c  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x14000c981  mov     edx, 6E6D7377h; Tag
0x14000c986  mov     rcx, rbx; P
0x14000c989  call    cs:__imp_ExFreePoolWithTag
0x14000c990  nop     dword ptr [rax+rax+00h]
0x14000c995  mov     eax, r15d
0x14000c998  jmp     short loc_14000C937
0x14000c99a  mov     eax, 0C000009Ah
0x14000c99f  jmp     short loc_14000C937
```
