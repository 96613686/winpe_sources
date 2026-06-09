# CWsmTrackingConfig::CTrackingConfig::Initialize(_WSM_TRACKING_CONFIG * const,bool)

- ea: `0x14000ab4c`
- end: `0x14000adaf`
- name: `?Initialize@CTrackingConfig@CWsmTrackingConfig@@IEAAJQEAU_WSM_TRACKING_CONFIG@@_N@Z`
- size: `611`
- prototype: `int(CWsmTrackingConfig::CTrackingConfig *__hidden this, struct _WSM_TRACKING_CONFIG *const, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14000a728`

## callees

- `0x140008bb0`
- `0x1400091cc`
- `0x14000a8c4`
- `0x14000ab4c`
- `0x14000d0a8`
- `0x14000d21c`
- `0x14000f9e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000ac85`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000acce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ad20`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ad9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ac85`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000acce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ad20`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ad9a`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::CTrackingConfig::Initialize(
        CWsmTrackingConfig::CTrackingConfig *this,
        struct _WSM_TRACKING_CONFIG *const a2,
        bool a3)
{
  int Instance; // edi
  bool v4; // r15
  __int64 result; // rax
  _QWORD *v8; // rax
  __int64 v9; // rcx
  __int64 *v10; // rax
  __int64 v11; // rcx
  unsigned int v12; // eax
  __int64 *v13; // r13
  __int64 *v14; // r14
  __int64 v15; // rbp
  struct CWsmTrackingConfig::CTrackingPathInfo **v16; // rax
  void ***v17; // r15
  __int64 v18; // rax
  PVOID v19; // rdx
  void ***v20; // r15
  __int64 v21; // rcx
  __int64 v22; // rax
  __int128 v23; // xmm0
  __int64 v24; // xmm1_8
  __int64 v25; // rcx
  PVOID v26; // r15
  __int64 v27; // rax
  PVOID v28; // rbx
  void ***v29; // [rsp+20h] [rbp-58h] BYREF
  void ****v30; // [rsp+28h] [rbp-50h]
  PVOID P; // [rsp+88h] [rbp+10h] BYREF
  bool v32; // [rsp+90h] [rbp+18h]

  v32 = a3;
  Instance = 0;
  v4 = a3;
  if ( !a2 )
    return (unsigned int)Instance;
  result = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 7) + 16LL))((char *)this + 56, *(_QWORD *)a2);
  if ( (int)result >= 0 )
  {
    v8 = (_QWORD *)*((_QWORD *)this + 8);
    v9 = v8 ? *v8 : 0LL;
    *((_QWORD *)this + 11) = v9;
    result = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 9) + 16LL))(
               (char *)this + 72,
               *((_QWORD *)a2 + 1));
    Instance = result;
    if ( (int)result >= 0 )
    {
      v10 = (__int64 *)*((_QWORD *)this + 10);
      if ( v10 )
        v11 = *v10;
      else
        v11 = 0;
      *((_QWORD *)this + 12) = v11;
      v12 = *((_DWORD *)a2 + 4);
      if ( v12 )
      {
        v13 = (__int64 *)((char *)this + 8);
        if ( !(unsigned __int8)utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>::resize(
                                 (char *)this + 8,
                                 v12) )
          return 3221225626LL;
        v14 = (__int64 *)((char *)this + 32);
        if ( !(unsigned __int8)utl::vector<_WSM_TRACKING_PATH_INFO,utl::allocator<_WSM_TRACKING_PATH_INFO>>::resize(
                                 (char *)this + 32,
                                 *((unsigned int *)a2 + 4)) )
          return 3221225626LL;
        v15 = 0;
        if ( *((_DWORD *)a2 + 4) )
        {
          while ( 1 )
          {
            P = 0;
            v16 = (struct CWsmTrackingConfig::CTrackingPathInfo **)utl::out_ptr<void,utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,>(
                                                                     &v29,
                                                                     &P);
            Instance = CWsmTrackingConfig::CTrackingPathInfo::CreateInstance(
                         (struct _WSM_TRACKING_PATH_INFO *const)(*((_QWORD *)a2 + 3) + 24 * v15),
                         v4,
                         v16);
            if ( v29 )
            {
              v17 = *v30;
              *v30 = v29;
              if ( v17 )
              {
                CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(v17);
                ExFreePoolWithTag(v17, 0x6E6D7377u);
              }
            }
            if ( Instance < 0 )
              break;
            v18 = *v13;
            v19 = P;
            P = 0;
            v20 = *(void ****)(v18 + 8 * v15);
            *(_QWORD *)(v18 + 8 * v15) = v19;
            if ( v20 )
            {
              CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(v20);
              ExFreePoolWithTag(v20, 0x6E6D7377u);
            }
            v21 = *(_QWORD *)(*v13 + 8 * v15);
            v22 = *v14;
            v23 = *(_OWORD *)(v21 + 72);
            v24 = *(_QWORD *)(v21 + 88);
            v25 = 3 * v15;
            *(_OWORD *)(v22 + 8 * v25) = v23;
            *(_QWORD *)(v22 + 8 * v25 + 16) = v24;
            v26 = P;
            if ( P )
            {
              CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo((void ***)P);
              ExFreePoolWithTag(v26, 0x6E6D7377u);
            }
            v4 = v32;
            v15 = (unsigned int)(v15 + 1);
            if ( (unsigned int)v15 >= *((_DWORD *)a2 + 4) )
              goto LABEL_23;
          }
          v28 = P;
          if ( P )
          {
            CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo((void ***)P);
            ExFreePoolWithTag(v28, 0x6E6D7377u);
          }
        }
        else
        {
LABEL_23:
          v27 = *((_QWORD *)this + 5) - *((_QWORD *)this + 4);
          *((_QWORD *)this + 14) = *v14;
          *((_DWORD *)this + 26) = -1431655765 * (v27 >> 3);
        }
      }
      return (unsigned int)Instance;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000ab4c  mov     [rsp+arg_0], rbx
0x14000ab51  mov     [rsp+arg_10], r8b
0x14000ab56  push    rbp
0x14000ab57  push    rsi
0x14000ab58  push    rdi
0x14000ab59  push    r12
0x14000ab5b  push    r13
0x14000ab5d  push    r14
0x14000ab5f  push    r15
0x14000ab61  sub     rsp, 40h
0x14000ab65  xor     edi, edi
0x14000ab67  mov     r15b, r8b
0x14000ab6a  mov     rsi, rdx
0x14000ab6d  mov     rbx, rcx
0x14000ab70  test    rdx, rdx
0x14000ab73  jz      loc_14000AD62
0x14000ab79  mov     rdx, [rdx]
0x14000ab7c  add     rcx, 38h ; '8'
0x14000ab80  mov     rax, [rcx]
0x14000ab83  mov     rax, [rax+10h]
0x14000ab87  call    _guard_dispatch_icall
0x14000ab8c  test    eax, eax
0x14000ab8e  js      loc_14000AD64
0x14000ab94  mov     rax, [rbx+40h]
0x14000ab98  test    rax, rax
0x14000ab9b  jz      short loc_14000ABA2
0x14000ab9d  mov     rcx, [rax]
0x14000aba0  jmp     short loc_14000ABA4
0x14000aba2  xor     ecx, ecx
0x14000aba4  mov     [rbx+58h], rcx
0x14000aba8  lea     rcx, [rbx+48h]
0x14000abac  mov     rax, [rcx]
0x14000abaf  mov     rdx, [rsi+8]
0x14000abb3  mov     rax, [rax+10h]
0x14000abb7  call    _guard_dispatch_icall
0x14000abbc  mov     edi, eax
0x14000abbe  test    eax, eax
0x14000abc0  js      loc_14000AD64
0x14000abc6  mov     rax, [rbx+50h]
0x14000abca  test    rax, rax
0x14000abcd  jz      short loc_14000ABD4
0x14000abcf  mov     rcx, [rax]
0x14000abd2  jmp     short loc_14000ABD6
0x14000abd4  xor     ecx, ecx
0x14000abd6  mov     [rbx+60h], rcx
0x14000abda  mov     eax, [rsi+10h]
0x14000abdd  test    eax, eax
0x14000abdf  jz      loc_14000AD62
0x14000abe5  lea     r13, [rbx+8]
0x14000abe9  mov     edx, eax
0x14000abeb  mov     rcx, r13
0x14000abee  call    ?resize@?$vector@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@2@@utl@@QEAA_N_K@Z; utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>::resize(unsigned __int64)
0x14000abf3  test    al, al
0x14000abf5  jz      loc_14000ADA8
0x14000abfb  mov     edx, [rsi+10h]
0x14000abfe  lea     r14, [rbx+20h]
0x14000ac02  mov     rcx, r14
0x14000ac05  call    ?resize@?$vector@U_WSM_TRACKING_PATH_INFO@@V?$allocator@U_WSM_TRACKING_PATH_INFO@@@utl@@@utl@@QEAA_N_K@Z; utl::vector<_WSM_TRACKING_PATH_INFO,utl::allocator<_WSM_TRACKING_PATH_INFO>>::resize(unsigned __int64)
0x14000ac0a  test    al, al
0x14000ac0c  jz      loc_14000ADA8
0x14000ac12  xor     ebp, ebp
0x14000ac14  cmp     [rsi+10h], ebp
0x14000ac17  jbe     loc_14000AD3F
0x14000ac1d  lea     rdx, [rsp+78h+P]
0x14000ac25  mov     [rsp+78h+P], 0
0x14000ac31  lea     rcx, [rsp+78h+var_58]
0x14000ac36  call    ??$out_ptr@XV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@0@@Z
0x14000ac3b  mov     rcx, [rsi+18h]
0x14000ac3f  lea     rdx, ds:0[rbp*2]
0x14000ac47  add     rdx, rbp
0x14000ac4a  mov     r8, rax; struct CWsmTrackingConfig::CTrackingPathInfo **
0x14000ac4d  lea     rcx, [rcx+rdx*8]; struct _WSM_TRACKING_PATH_INFO *
0x14000ac51  mov     dl, r15b; bool
0x14000ac54  call    ?CreateInstance@CTrackingPathInfo@CWsmTrackingConfig@@SAJQEAU_WSM_TRACKING_PATH_INFO@@_NPEAPEAV12@@Z; CWsmTrackingConfig::CTrackingPathInfo::CreateInstance(_WSM_TRACKING_PATH_INFO * const,bool,CWsmTrackingConfig::CTrackingPathInfo * *)
0x14000ac59  mov     rcx, [rsp+78h+var_58]
0x14000ac5e  mov     edi, eax
0x14000ac60  test    rcx, rcx
0x14000ac63  jz      short loc_14000AC91
0x14000ac65  mov     rax, [rsp+78h+var_50]
0x14000ac6a  mov     r15, [rax]
0x14000ac6d  mov     [rax], rcx
0x14000ac70  test    r15, r15
0x14000ac73  jz      short loc_14000AC91
0x14000ac75  mov     rcx, r15; this
0x14000ac78  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x14000ac7d  mov     edx, 6E6D7377h; Tag
0x14000ac82  mov     rcx, r15; P
0x14000ac85  call    cs:__imp_ExFreePoolWithTag
0x14000ac8c  nop     dword ptr [rax+rax+00h]
0x14000ac91  test    edi, edi
0x14000ac93  js      loc_14000AD7D
0x14000ac99  mov     rax, [r13+0]
0x14000ac9d  mov     rdx, [rsp+78h+P]
0x14000aca5  mov     [rsp+78h+P], 0
0x14000acb1  mov     r15, [rax+rbp*8]
0x14000acb5  mov     [rax+rbp*8], rdx
0x14000acb9  test    r15, r15
0x14000acbc  jz      short loc_14000ACDA
0x14000acbe  mov     rcx, r15; this
0x14000acc1  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x14000acc6  mov     edx, 6E6D7377h; Tag
0x14000accb  mov     rcx, r15; P
0x14000acce  call    cs:__imp_ExFreePoolWithTag
0x14000acd5  nop     dword ptr [rax+rax+00h]
0x14000acda  mov     rax, [r13+0]
0x14000acde  mov     rcx, [rax+rbp*8]
0x14000ace2  mov     rax, [r14]
0x14000ace5  movups  xmm0, xmmword ptr [rcx+48h]
0x14000ace9  movsd   xmm1, qword ptr [rcx+58h]
0x14000acee  lea     rcx, ds:0[rbp*2]
0x14000acf6  add     rcx, rbp
0x14000acf9  movups  xmmword ptr [rax+rcx*8], xmm0
0x14000acfd  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x14000ad03  mov     r15, [rsp+78h+P]
0x14000ad0b  test    r15, r15
0x14000ad0e  jz      short loc_14000AD2C
0x14000ad10  mov     rcx, r15; this
0x14000ad13  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x14000ad18  mov     edx, 6E6D7377h; Tag
0x14000ad1d  mov     rcx, r15; P
0x14000ad20  call    cs:__imp_ExFreePoolWithTag
0x14000ad27  nop     dword ptr [rax+rax+00h]
0x14000ad2c  mov     r15b, [rsp+78h+arg_10]
0x14000ad34  inc     ebp
0x14000ad36  cmp     ebp, [rsi+10h]
0x14000ad39  jb      loc_14000AC1D
0x14000ad3f  mov     rcx, [r14]
0x14000ad42  mov     rdx, 0AAAAAAAAAAAAAAABh
0x14000ad4c  mov     rax, [r14+8]
0x14000ad50  sub     rax, rcx
0x14000ad53  mov     [rbx+70h], rcx
0x14000ad57  sar     rax, 3
0x14000ad5b  imul    rax, rdx
0x14000ad5f  mov     [rbx+68h], eax
0x14000ad62  mov     eax, edi
0x14000ad64  mov     rbx, [rsp+78h+arg_0]
0x14000ad6c  add     rsp, 40h
0x14000ad70  pop     r15
0x14000ad72  pop     r14
0x14000ad74  pop     r13
0x14000ad76  pop     r12
0x14000ad78  pop     rdi
0x14000ad79  pop     rsi
0x14000ad7a  pop     rbp
0x14000ad7b  retn
0x14000ad7d  mov     rbx, [rsp+78h+P]
0x14000ad85  test    rbx, rbx
0x14000ad88  jz      short loc_14000AD62
0x14000ad8a  mov     rcx, rbx; this
0x14000ad8d  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x14000ad92  mov     edx, 6E6D7377h; Tag
0x14000ad97  mov     rcx, rbx; P
0x14000ad9a  call    cs:__imp_ExFreePoolWithTag
0x14000ada1  nop     dword ptr [rax+rax+00h]
0x14000ada6  jmp     short loc_14000AD62
0x14000ada8  mov     eax, 0C000009Ah
0x14000adad  jmp     short loc_14000AD64
```
