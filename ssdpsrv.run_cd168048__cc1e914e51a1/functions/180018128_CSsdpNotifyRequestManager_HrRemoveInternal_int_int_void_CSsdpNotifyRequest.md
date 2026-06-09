# CSsdpNotifyRequestManager::HrRemoveInternal(int,int,void *,CSsdpNotifyRequest *)

- ea: `0x180018128`
- end: `0x180018441`
- name: `?HrRemoveInternal@CSsdpNotifyRequestManager@@AEAAJHHPEAXPEAVCSsdpNotifyRequest@@@Z`
- size: `793`
- prototype: `__int64 __fastcall(CSsdpNotifyRequestManager *__hidden this, int, int, void *, struct CSsdpNotifyRequest *)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x180026748`
- `0x18002f900`
- `0x180030ab0`
- `0x180030e30`

## callees

- `0x18000a934`
- `0x18001784c`
- `0x180018128`
- `0x180019920`
- `0x18001aeb4`
- `0x18001c374`
- `0x180024490`
- `0x1800271fc`
- `0x18002e8ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800181bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001823f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800182c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018372`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800181bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001823f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800182c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018372`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018152`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800181cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018255`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018334`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018152`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800181cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018255`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018334`

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
  char *v21; // [rsp+20h] [rbp-18h] BYREF
  _QWORD v22[2]; // [rsp+28h] [rbp-10h] BYREF
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
  v21 = (char *)this + 136;
  if ( *((_QWORD *)this + 17) )
  {
    v22[0] = 0;
    do
    {
      if ( (unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem(&v21, v22) )
        break;
    }
    while ( !(a3 || a4 && *(void **)(v22[0] + 200LL) == a4 || v10 && (struct CSsdpNotifyRequest *)v22[0] == v10
            ? CUList<CSsdpCacheEntry>::Iterator::HrMoveToList(&v21, &v23)
            : (unsigned int)CUList<__int64>::Iterator::HrNext(&v21)) );
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  v14 = (char *)this + 184;
  v22[0] = (char *)this + 184;
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
  v22[0] = &v23;
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
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids);
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
0x180018128  push    rbp
0x18001812a  push    rbx
0x18001812b  push    rsi
0x18001812c  push    rdi
0x18001812d  push    r12
0x18001812f  push    r13
0x180018131  push    r14
0x180018133  push    r15
0x180018135  mov     rbp, rsp
0x180018138  sub     rsp, 38h
0x18001813c  mov     r15, rcx
0x18001813f  xor     esi, esi
0x180018141  add     rcx, 30h ; '0'; lpCriticalSection
0x180018145  mov     [rbp+arg_0], rsi
0x180018149  mov     rdi, r9
0x18001814c  mov     r12d, r8d
0x18001814f  mov     r13d, edx
0x180018152  call    cs:__imp_EnterCriticalSection
0x180018159  nop     dword ptr [rax+rax+00h]
0x18001815e  mov     r14, [rbp+arg_20]
0x180018162  lea     rax, [r15+58h]
0x180018166  xor     r8d, r8d
0x180018169  jmp     short loc_1800181B4
0x18001816b  test    rax, rax
0x18001816e  jz      short loc_1800181B9
0x180018170  mov     rdx, [rax]
0x180018173  test    rdx, rdx
0x180018176  jz      short loc_1800181B9
0x180018178  test    r12d, r12d
0x18001817b  jnz     short loc_1800181A3
0x18001817d  lea     rcx, [rdx+8]
0x180018181  test    rdi, rdi
0x180018184  jz      short loc_18001818F
0x180018186  cmp     [rcx+0C8h], rdi
0x18001818d  jz      short loc_1800181A3
0x18001818f  test    r14, r14
0x180018192  jz      short loc_180018199
0x180018194  cmp     rcx, r14
0x180018197  jz      short loc_1800181A3
0x180018199  cmp     [rdx], r8
0x18001819c  jz      short loc_1800181B9
0x18001819e  mov     rax, rdx
0x1800181a1  jmp     short loc_18001816B
0x1800181a3  mov     rcx, [rdx]
0x1800181a6  mov     [rax], rcx
0x1800181a9  mov     rcx, [rbp+arg_0]
0x1800181ad  mov     [rdx], rcx
0x1800181b0  mov     [rbp+arg_0], rdx
0x1800181b4  cmp     [rax], r8
0x1800181b7  jnz     short loc_18001816B
0x1800181b9  lea     rcx, [r15+30h]; lpCriticalSection
0x1800181bd  call    cs:__imp_LeaveCriticalSection
0x1800181c4  nop     dword ptr [rax+rax+00h]
0x1800181c9  lea     rcx, [r15+60h]; lpCriticalSection
0x1800181cd  call    cs:__imp_EnterCriticalSection
0x1800181d4  nop     dword ptr [rax+rax+00h]
0x1800181d9  lea     rax, [r15+88h]
0x1800181e0  mov     [rbp+var_18], rax
0x1800181e4  cmp     [rax], rsi
0x1800181e7  jz      short loc_18001823B
0x1800181e9  mov     [rbp+var_10], rsi
0x1800181ed  lea     rdx, [rbp+var_10]
0x1800181f1  lea     rcx, [rbp+var_18]
0x1800181f5  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x1800181fa  test    eax, eax
0x1800181fc  jnz     short loc_18001823B
0x1800181fe  test    r12d, r12d
0x180018201  jnz     short loc_18001822A
0x180018203  mov     rax, [rbp+var_10]
0x180018207  test    rdi, rdi
0x18001820a  jz      short loc_180018215
0x18001820c  cmp     [rax+0C8h], rdi
0x180018213  jz      short loc_18001822A
0x180018215  test    r14, r14
0x180018218  jz      short loc_18001821F
0x18001821a  cmp     rax, r14
0x18001821d  jz      short loc_18001822A
0x18001821f  lea     rcx, [rbp+var_18]
0x180018223  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x180018228  jmp     short loc_180018237
0x18001822a  lea     rdx, [rbp+arg_0]
0x18001822e  lea     rcx, [rbp+var_18]
0x180018232  call    ?HrMoveToList@Iterator@?$CUList@VCSsdpCacheEntry@@@@QEAAJAEAV2@@Z; CUList<CSsdpCacheEntry>::Iterator::HrMoveToList(CUList<CSsdpCacheEntry> &)
0x180018237  test    eax, eax
0x180018239  jz      short loc_1800181ED
0x18001823b  lea     rcx, [r15+60h]; lpCriticalSection
0x18001823f  call    cs:__imp_LeaveCriticalSection
0x180018246  nop     dword ptr [rax+rax+00h]
0x18001824b  lea     rdi, [r15+90h]
0x180018252  mov     rcx, rdi; lpCriticalSection
0x180018255  call    cs:__imp_EnterCriticalSection
0x18001825c  nop     dword ptr [rax+rax+00h]
0x180018261  lea     rax, [r15+0B8h]
0x180018268  mov     [rbp+var_10], rax
0x18001826c  cmp     [r15+0B8h], rsi
0x180018273  jz      short loc_1800182C2
0x180018275  test    rax, rax
0x180018278  jz      short loc_1800182C2
0x18001827a  mov     rcx, [rax]
0x18001827d  test    rcx, rcx
0x180018280  jz      short loc_1800182C2
0x180018282  test    r12d, r12d
0x180018285  jnz     short loc_1800182A4
0x180018287  mov     ecx, [rcx+0F4h]
0x18001828d  test    ecx, ecx
0x18001828f  jnz     short loc_1800182A4
0x180018291  lea     rcx, [rbp+var_10]
0x180018295  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x18001829a  test    eax, eax
0x18001829c  jnz     short loc_1800182C2
0x18001829e  mov     rax, [rbp+var_10]
0x1800182a2  jmp     short loc_180018275
0x1800182a4  mov     rdx, [rax]
0x1800182a7  test    rdx, rdx
0x1800182aa  jz      short loc_1800182C2
0x1800182ac  mov     rcx, [rdx]
0x1800182af  mov     [rax], rcx
0x1800182b2  mov     rcx, [rbp+arg_0]
0x1800182b6  mov     [rdx], rcx
0x1800182b9  mov     [rbp+arg_0], rdx
0x1800182bd  cmp     [rax], rsi
0x1800182c0  jnz     short loc_180018275
0x1800182c2  mov     rcx, rdi; lpCriticalSection
0x1800182c5  call    cs:__imp_LeaveCriticalSection
0x1800182cc  nop     dword ptr [rax+rax+00h]
0x1800182d1  lea     rbx, [rbp+arg_0]
0x1800182d5  mov     [rbp+var_10], rbx
0x1800182d9  cmp     [rbp+arg_0], rsi
0x1800182dd  jz      loc_18001841F
0x1800182e3  test    rbx, rbx
0x1800182e6  jz      loc_1800183EA
0x1800182ec  mov     rax, [rbx]
0x1800182ef  test    rax, rax
0x1800182f2  jz      loc_1800183EA
0x1800182f8  lea     r14, [rax+8]
0x1800182fc  test    r13d, r13d
0x1800182ff  jnz     short loc_180018310
0x180018301  mov     rdx, r14; void *
0x180018304  lea     rcx, ?s_instance@CSsdpRundownSupport@@0V1@A; lpCriticalSection
0x18001830b  call    ?RemoveRundownItem@CSsdpRundownSupport@@QEAAXPEAX@Z; CSsdpRundownSupport::RemoveRundownItem(void *)
0x180018310  mov     edx, r12d; int
0x180018313  mov     rcx, r14; this
0x180018316  call    ?HrShutdown@CSsdpNotifyRequest@@QEAAJH@Z; CSsdpNotifyRequest::HrShutdown(int)
0x18001831b  mov     esi, eax
0x18001831d  cmp     eax, 8000000Ah
0x180018322  jnz     loc_1800183C1
0x180018328  test    r12d, r12d
0x18001832b  jnz     loc_1800183C1
0x180018331  mov     rcx, rdi; lpCriticalSection
0x180018334  call    cs:__imp_EnterCriticalSection
0x18001833b  nop     dword ptr [rax+rax+00h]
0x180018340  mov     rcx, [rbx]
0x180018343  test    rcx, rcx
0x180018346  jz      short loc_18001836A
0x180018348  mov     rax, [rcx]
0x18001834b  xor     esi, esi
0x18001834d  mov     [rbx], rax
0x180018350  mov     rax, [r15+0B8h]
0x180018357  mov     [rcx], rax
0x18001835a  mov     [r15+0B8h], rcx
0x180018361  cmp     [rbx], rsi
0x180018364  setz    sil
0x180018368  jmp     short loc_18001836F
0x18001836a  mov     esi, 8000FFFFh
0x18001836f  mov     rcx, rdi; lpCriticalSection
0x180018372  call    cs:__imp_LeaveCriticalSection
0x180018379  nop     dword ptr [rax+rax+00h]
0x18001837e  test    esi, esi
0x180018380  jns     short loc_1800183DA
0x180018382  mov     rcx, cs:WPP_GLOBAL_Control
0x180018389  lea     rax, WPP_GLOBAL_Control
0x180018390  cmp     rcx, rax
0x180018393  jz      short loc_1800183B3
0x180018395  test    byte ptr [rcx+1Ch], 8
0x180018399  jz      short loc_1800183B3
0x18001839b  mov     rcx, [rcx+10h]
0x18001839f  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x1800183a6  mov     edx, 65h ; 'e'
0x1800183ab  mov     r9, r14
0x1800183ae  call    WPP_SF_q
0x1800183b3  xor     edx, edx; int
0x1800183b5  mov     rcx, r14; this
0x1800183b8  call    ?HrShutdown@CSsdpNotifyRequest@@QEAAJH@Z; CSsdpNotifyRequest::HrShutdown(int)
0x1800183bd  mov     esi, eax
0x1800183bf  jmp     short loc_1800183D2
0x1800183c1  lea     rcx, [rbp+var_10]
0x1800183c5  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x1800183ca  test    eax, eax
0x1800183cc  jnz     short loc_1800183EA
0x1800183ce  mov     rbx, [rbp+var_10]
0x1800183d2  cmp     esi, 8000000Ah
0x1800183d8  jz      short loc_1800183E3
0x1800183da  cmp     esi, 1
0x1800183dd  jnz     loc_1800182E3
0x1800183e3  xor     esi, esi
0x1800183e5  jmp     loc_1800182E3
0x1800183ea  test    esi, esi
0x1800183ec  jz      short loc_18001841F
0x1800183ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800183f5  lea     rax, WPP_GLOBAL_Control
0x1800183fc  cmp     rcx, rax
0x1800183ff  jz      short loc_18001841F
0x180018401  test    byte ptr [rcx+1Ch], 1
0x180018405  jz      short loc_18001841F
0x180018407  mov     rcx, [rcx+10h]
0x18001840b  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x180018412  mov     edx, 66h ; 'f'
0x180018417  mov     r9d, esi
0x18001841a  call    WPP_SF_d
0x18001841f  mov     rcx, [rbp+arg_0]; void *
0x180018423  test    rcx, rcx
0x180018426  jz      short loc_18001842D
0x180018428  call    ??_GNode@?$CUList@VCSsdpNotifyRequest@@@@QEAAPEAXI@Z; CUList<CSsdpNotifyRequest>::Node::`scalar deleting destructor'(uint)
0x18001842d  mov     eax, esi
0x18001842f  add     rsp, 38h
0x180018433  pop     r15
0x180018435  pop     r14
0x180018437  pop     r13
0x180018439  pop     r12
0x18001843b  pop     rdi
0x18001843c  pop     rsi
0x18001843d  pop     rbx
0x18001843e  pop     rbp
0x18001843f  retn
```
