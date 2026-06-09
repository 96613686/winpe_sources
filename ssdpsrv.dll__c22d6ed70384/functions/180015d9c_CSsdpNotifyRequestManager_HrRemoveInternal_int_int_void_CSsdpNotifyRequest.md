# CSsdpNotifyRequestManager::HrRemoveInternal(int,int,void *,CSsdpNotifyRequest *)

- ea: `0x180015d9c`
- end: `0x180016084`
- name: `?HrRemoveInternal@CSsdpNotifyRequestManager@@AEAAJHHPEAXPEAVCSsdpNotifyRequest@@@Z`
- size: `744`
- prototype: `__int64 __fastcall(CSsdpNotifyRequestManager *__hidden this, int, int, void *, struct CSsdpNotifyRequest *)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x180024bec`
- `0x18002d870`
- `0x18002e8fc`
- `0x18002ec20`

## callees

- `0x1800092f4`
- `0x18001528c`
- `0x180015d9c`
- `0x1800186a0`
- `0x180019bac`
- `0x18001b070`
- `0x180022a80`
- `0x1800255a8`
- `0x18002c8cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015e2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015ea1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015f1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015fbc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015e2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015ea1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015f1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015fbc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015dc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015e35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015eb1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015f84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015dc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015e35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015eb1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015f84`

## pseudocode

```c
__int64 __fastcall CSsdpNotifyRequestManager::HrRemoveInternal(
        CSsdpNotifyRequestManager *this,
        int a2,
        int a3,
        void *a4,
        struct CSsdpNotifyRequest *a5)
{
  int v6; // esi
  struct CSsdpNotifyRequest *v10; // r14
  void ***v11; // rax
  void **v12; // rdx
  char *v14; // rax
  void **v15; // rdx
  void **v16; // rbx
  char *v17; // rax
  CSsdpNotifyRequest *v18; // r14
  void **v19; // rcx
  __int64 *v21; // [rsp+20h] [rbp-18h] BYREF
  _QWORD **v22[2]; // [rsp+28h] [rbp-10h] BYREF
  void *v23; // [rsp+80h] [rbp+48h] BYREF

  v6 = 0;
  v23 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v10 = a5;
  v11 = (void ***)((char *)this + 88);
LABEL_12:
  if ( *v11 )
  {
    while ( v11 )
    {
      v12 = *v11;
      if ( !*v11 )
        break;
      if ( a3 || a4 && v12[26] == a4 || v10 && v12 + 1 == (void **)v10 )
      {
        *v11 = (void **)*v12;
        *v12 = v23;
        v23 = v12;
        goto LABEL_12;
      }
      if ( !*v12 )
        break;
      v11 = (void ***)*v11;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v21 = (__int64 *)((char *)this + 136);
  if ( *((_QWORD *)this + 17) )
  {
    v22[0] = 0;
    do
    {
      if ( (unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem(&v21, v22) )
        break;
    }
    while ( !(a3 || a4 && *((void **)v22[0] + 25) == a4 || v10 && (struct CSsdpNotifyRequest *)v22[0] == v10
            ? CUList<CSsdpCacheEntry>::Iterator::HrMoveToList((_QWORD ***)&v21, &v23)
            : (unsigned int)CUList<__int64>::Iterator::HrNext((_QWORD ***)&v21)) );
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  v14 = (char *)this + 184;
  v22[0] = (_QWORD **)((char *)this + 184);
  if ( *((_QWORD *)this + 23) )
  {
    while ( v14 && *(_QWORD *)v14 )
    {
      if ( a3 || *(_DWORD *)(*(_QWORD *)v14 + 244LL) )
      {
        v15 = *(void ***)v14;
        if ( !*(_QWORD *)v14 )
          break;
        *(_QWORD *)v14 = *v15;
        *v15 = v23;
        v23 = v15;
        if ( !*(_QWORD *)v14 )
          break;
      }
      else
      {
        if ( (unsigned int)CUList<__int64>::Iterator::HrNext(v22) )
          break;
        v14 = (char *)v22[0];
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  v16 = &v23;
  v22[0] = (_QWORD **)&v23;
  if ( !v23 )
    goto LABEL_57;
  while ( v16 )
  {
    v17 = (char *)*v16;
    if ( !*v16 )
      break;
    v18 = (CSsdpNotifyRequest *)(v17 + 8);
    if ( !a2 )
      CSsdpRundownSupport::RemoveRundownItem(&CSsdpRundownSupport::s_instance, v17 + 8);
    v6 = CSsdpNotifyRequest::HrShutdown(v18, a3);
    if ( v6 != -2147483638 || a3 )
    {
      if ( (unsigned int)CUList<__int64>::Iterator::HrNext(v22) )
        break;
      v16 = (void **)v22[0];
LABEL_50:
      if ( v6 == -2147483638 )
        goto LABEL_52;
      goto LABEL_51;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
    v19 = (void **)*v16;
    if ( *v16 )
    {
      *v16 = *v19;
      *v19 = (void *)*((_QWORD *)this + 23);
      *((_QWORD *)this + 23) = v19;
      v6 = *v16 == 0;
    }
    else
    {
      v6 = -2147418113;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids, v18);
      v6 = CSsdpNotifyRequest::HrShutdown(v18, 0);
      goto LABEL_50;
    }
LABEL_51:
    if ( v6 == 1 )
LABEL_52:
      v6 = 0;
  }
  if ( v6 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      102,
      WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids,
      (unsigned int)v6);
LABEL_57:
  if ( v23 )
    CUList<CSsdpNotifyRequest>::Node::`scalar deleting destructor'(v23);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180015d9c  push    rbp
0x180015d9e  push    rbx
0x180015d9f  push    rsi
0x180015da0  push    rdi
0x180015da1  push    r12
0x180015da3  push    r13
0x180015da5  push    r14
0x180015da7  push    r15
0x180015da9  mov     rbp, rsp
0x180015dac  sub     rsp, 38h
0x180015db0  mov     r15, rcx
0x180015db3  xor     esi, esi
0x180015db5  add     rcx, 30h ; '0'; lpCriticalSection
0x180015db9  mov     [rbp+arg_0], rsi
0x180015dbd  mov     rdi, r9
0x180015dc0  mov     r12d, r8d
0x180015dc3  mov     r13d, edx
0x180015dc6  call    cs:__imp_EnterCriticalSection
0x180015dcc  mov     r14, [rbp+arg_20]
0x180015dd0  lea     rax, [r15+58h]
0x180015dd4  xor     r8d, r8d
0x180015dd7  jmp     short loc_180015E22
0x180015dd9  test    rax, rax
0x180015ddc  jz      short loc_180015E27
0x180015dde  mov     rdx, [rax]
0x180015de1  test    rdx, rdx
0x180015de4  jz      short loc_180015E27
0x180015de6  test    r12d, r12d
0x180015de9  jnz     short loc_180015E11
0x180015deb  lea     rcx, [rdx+8]
0x180015def  test    rdi, rdi
0x180015df2  jz      short loc_180015DFD
0x180015df4  cmp     [rcx+0C8h], rdi
0x180015dfb  jz      short loc_180015E11
0x180015dfd  test    r14, r14
0x180015e00  jz      short loc_180015E07
0x180015e02  cmp     rcx, r14
0x180015e05  jz      short loc_180015E11
0x180015e07  cmp     [rdx], r8
0x180015e0a  jz      short loc_180015E27
0x180015e0c  mov     rax, rdx
0x180015e0f  jmp     short loc_180015DD9
0x180015e11  mov     rcx, [rdx]
0x180015e14  mov     [rax], rcx
0x180015e17  mov     rcx, [rbp+arg_0]
0x180015e1b  mov     [rdx], rcx
0x180015e1e  mov     [rbp+arg_0], rdx
0x180015e22  cmp     [rax], r8
0x180015e25  jnz     short loc_180015DD9
0x180015e27  lea     rcx, [r15+30h]; lpCriticalSection
0x180015e2b  call    cs:__imp_LeaveCriticalSection
0x180015e31  lea     rcx, [r15+60h]; lpCriticalSection
0x180015e35  call    cs:__imp_EnterCriticalSection
0x180015e3b  lea     rax, [r15+88h]
0x180015e42  mov     [rbp+var_18], rax
0x180015e46  cmp     [rax], rsi
0x180015e49  jz      short loc_180015E9D
0x180015e4b  mov     [rbp+var_10], rsi
0x180015e4f  lea     rdx, [rbp+var_10]
0x180015e53  lea     rcx, [rbp+var_18]
0x180015e57  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x180015e5c  test    eax, eax
0x180015e5e  jnz     short loc_180015E9D
0x180015e60  test    r12d, r12d
0x180015e63  jnz     short loc_180015E8C
0x180015e65  mov     rax, [rbp+var_10]
0x180015e69  test    rdi, rdi
0x180015e6c  jz      short loc_180015E77
0x180015e6e  cmp     [rax+0C8h], rdi
0x180015e75  jz      short loc_180015E8C
0x180015e77  test    r14, r14
0x180015e7a  jz      short loc_180015E81
0x180015e7c  cmp     rax, r14
0x180015e7f  jz      short loc_180015E8C
0x180015e81  lea     rcx, [rbp+var_18]
0x180015e85  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x180015e8a  jmp     short loc_180015E99
0x180015e8c  lea     rdx, [rbp+arg_0]
0x180015e90  lea     rcx, [rbp+var_18]
0x180015e94  call    ?HrMoveToList@Iterator@?$CUList@VCSsdpCacheEntry@@@@QEAAJAEAV2@@Z; CUList<CSsdpCacheEntry>::Iterator::HrMoveToList(CUList<CSsdpCacheEntry> &)
0x180015e99  test    eax, eax
0x180015e9b  jz      short loc_180015E4F
0x180015e9d  lea     rcx, [r15+60h]; lpCriticalSection
0x180015ea1  call    cs:__imp_LeaveCriticalSection
0x180015ea7  lea     rdi, [r15+90h]
0x180015eae  mov     rcx, rdi; lpCriticalSection
0x180015eb1  call    cs:__imp_EnterCriticalSection
0x180015eb7  lea     rax, [r15+0B8h]
0x180015ebe  mov     [rbp+var_10], rax
0x180015ec2  cmp     [r15+0B8h], rsi
0x180015ec9  jz      short loc_180015F18
0x180015ecb  test    rax, rax
0x180015ece  jz      short loc_180015F18
0x180015ed0  mov     rcx, [rax]
0x180015ed3  test    rcx, rcx
0x180015ed6  jz      short loc_180015F18
0x180015ed8  test    r12d, r12d
0x180015edb  jnz     short loc_180015EFA
0x180015edd  mov     ecx, [rcx+0F4h]
0x180015ee3  test    ecx, ecx
0x180015ee5  jnz     short loc_180015EFA
0x180015ee7  lea     rcx, [rbp+var_10]
0x180015eeb  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x180015ef0  test    eax, eax
0x180015ef2  jnz     short loc_180015F18
0x180015ef4  mov     rax, [rbp+var_10]
0x180015ef8  jmp     short loc_180015ECB
0x180015efa  mov     rdx, [rax]
0x180015efd  test    rdx, rdx
0x180015f00  jz      short loc_180015F18
0x180015f02  mov     rcx, [rdx]
0x180015f05  mov     [rax], rcx
0x180015f08  mov     rcx, [rbp+arg_0]
0x180015f0c  mov     [rdx], rcx
0x180015f0f  mov     [rbp+arg_0], rdx
0x180015f13  cmp     [rax], rsi
0x180015f16  jnz     short loc_180015ECB
0x180015f18  mov     rcx, rdi; lpCriticalSection
0x180015f1b  call    cs:__imp_LeaveCriticalSection
0x180015f21  lea     rbx, [rbp+arg_0]
0x180015f25  mov     [rbp+var_10], rbx
0x180015f29  cmp     [rbp+arg_0], rsi
0x180015f2d  jz      loc_180016063
0x180015f33  test    rbx, rbx
0x180015f36  jz      loc_18001602E
0x180015f3c  mov     rax, [rbx]
0x180015f3f  test    rax, rax
0x180015f42  jz      loc_18001602E
0x180015f48  lea     r14, [rax+8]
0x180015f4c  test    r13d, r13d
0x180015f4f  jnz     short loc_180015F60
0x180015f51  mov     rdx, r14; void *
0x180015f54  lea     rcx, ?s_instance@CSsdpRundownSupport@@0V1@A; lpCriticalSection
0x180015f5b  call    ?RemoveRundownItem@CSsdpRundownSupport@@QEAAXPEAX@Z; CSsdpRundownSupport::RemoveRundownItem(void *)
0x180015f60  mov     edx, r12d; int
0x180015f63  mov     rcx, r14; this
0x180015f66  call    ?HrShutdown@CSsdpNotifyRequest@@QEAAJH@Z; CSsdpNotifyRequest::HrShutdown(int)
0x180015f6b  mov     esi, eax
0x180015f6d  cmp     eax, 8000000Ah
0x180015f72  jnz     loc_180016005
0x180015f78  test    r12d, r12d
0x180015f7b  jnz     loc_180016005
0x180015f81  mov     rcx, rdi; lpCriticalSection
0x180015f84  call    cs:__imp_EnterCriticalSection
0x180015f8a  mov     rcx, [rbx]
0x180015f8d  test    rcx, rcx
0x180015f90  jz      short loc_180015FB4
0x180015f92  mov     rax, [rcx]
0x180015f95  xor     esi, esi
0x180015f97  mov     [rbx], rax
0x180015f9a  mov     rax, [r15+0B8h]
0x180015fa1  mov     [rcx], rax
0x180015fa4  mov     [r15+0B8h], rcx
0x180015fab  cmp     [rbx], rsi
0x180015fae  setz    sil
0x180015fb2  jmp     short loc_180015FB9
0x180015fb4  mov     esi, 8000FFFFh
0x180015fb9  mov     rcx, rdi; lpCriticalSection
0x180015fbc  call    cs:__imp_LeaveCriticalSection
0x180015fc2  test    esi, esi
0x180015fc4  jns     short loc_18001601E
0x180015fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180015fcd  lea     rax, WPP_GLOBAL_Control
0x180015fd4  cmp     rcx, rax
0x180015fd7  jz      short loc_180015FF7
0x180015fd9  test    byte ptr [rcx+1Ch], 8
0x180015fdd  jz      short loc_180015FF7
0x180015fdf  mov     rcx, [rcx+10h]
0x180015fe3  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x180015fea  mov     edx, 65h ; 'e'
0x180015fef  mov     r9, r14
0x180015ff2  call    WPP_SF_q
0x180015ff7  xor     edx, edx; int
0x180015ff9  mov     rcx, r14; this
0x180015ffc  call    ?HrShutdown@CSsdpNotifyRequest@@QEAAJH@Z; CSsdpNotifyRequest::HrShutdown(int)
0x180016001  mov     esi, eax
0x180016003  jmp     short loc_180016016
0x180016005  lea     rcx, [rbp+var_10]
0x180016009  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x18001600e  test    eax, eax
0x180016010  jnz     short loc_18001602E
0x180016012  mov     rbx, [rbp+var_10]
0x180016016  cmp     esi, 8000000Ah
0x18001601c  jz      short loc_180016027
0x18001601e  cmp     esi, 1
0x180016021  jnz     loc_180015F33
0x180016027  xor     esi, esi
0x180016029  jmp     loc_180015F33
0x18001602e  test    esi, esi
0x180016030  jz      short loc_180016063
0x180016032  mov     rcx, cs:WPP_GLOBAL_Control
0x180016039  lea     rax, WPP_GLOBAL_Control
0x180016040  cmp     rcx, rax
0x180016043  jz      short loc_180016063
0x180016045  test    byte ptr [rcx+1Ch], 1
0x180016049  jz      short loc_180016063
0x18001604b  mov     rcx, [rcx+10h]
0x18001604f  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x180016056  mov     edx, 66h ; 'f'
0x18001605b  mov     r9d, esi
0x18001605e  call    WPP_SF_d
0x180016063  mov     rcx, [rbp+arg_0]; void *
0x180016067  test    rcx, rcx
0x18001606a  jz      short loc_180016071
0x18001606c  call    ??_GNode@?$CUList@VCSsdpNotifyRequest@@@@QEAAPEAXI@Z; CUList<CSsdpNotifyRequest>::Node::`scalar deleting destructor'(uint)
0x180016071  mov     eax, esi
0x180016073  add     rsp, 38h
0x180016077  pop     r15
0x180016079  pop     r14
0x18001607b  pop     r13
0x18001607d  pop     r12
0x18001607f  pop     rdi
0x180016080  pop     rsi
0x180016081  pop     rbx
0x180016082  pop     rbp
0x180016083  retn
```
