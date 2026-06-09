# SamHandleForDomain(void *,ulong,ulong,void * *,void * *)

- ea: `0x180003660`
- end: `0x1800037d1`
- name: `?SamHandleForDomain@@YAJPEAXKKPEAPEAX1@Z`
- size: `369`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int, void **, void **)`
- caller_count: `8`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000f168`
- `0x180010230`
- `0x1800119fc`
- `0x180011e80`
- `0x1800123c0`
- `0x1800125e8`
- `0x1800126c0`
- `0x180012acc`

## callees

- `0x180003660`
- `0x1800037e0`
- `0x180012f18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800037b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800037b8`
- `SAMLIB!SamOpenDomain` at `0x180003723`
- `SAMLIB!SamOpenDomain` at `0x180003723`
- `SAMLIB!SamConnect` at `0x1800036fa`
- `SAMLIB!SamConnect` at `0x1800036fa`
- `SAMLIB!SamCloseHandle` at `0x180003752`
- `SAMLIB!SamCloseHandle` at `0x180003752`

## pseudocode

```c
__int64 __fastcall SamHandleForDomain(void *a1, unsigned int a2, unsigned int a3, void **a4, void **a5)
{
  void **v5; // r15
  void *v9; // rdi
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // esi
  int v13; // ebx
  int v14; // ebx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  _QWORD v18[4]; // [rsp+20h] [rbp-78h] BYREF
  __int128 v19; // [rsp+40h] [rbp-58h]
  LPVOID pv; // [rsp+A0h] [rbp+8h] BYREF

  pv = a1;
  v5 = a5;
  *a4 = 0;
  v9 = a1;
  *v5 = 0;
  if ( a1 )
  {
    v12 = 0;
  }
  else
  {
    v10 = CSGetAccountDomainSid(&pv);
    v9 = pv;
    v11 = v10;
    v12 = 1;
    if ( v10 < 0 )
      goto LABEL_16;
  }
  v18[0] = 48;
  pv = 0;
  memset(&v18[1], 0, 24);
  v19 = 0;
  v13 = SamConnect(0, &pv, a2, v18);
  if ( v13 < 0 )
  {
    v11 = v13 | 0x10000000;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v16 = 35;
      goto LABEL_14;
    }
  }
  else
  {
    a5 = 0;
    v14 = SamOpenDomain(pv, a3, v9, &a5);
    if ( v14 >= 0 )
    {
      v11 = 0;
      *v5 = a5;
      *a4 = pv;
      goto LABEL_15;
    }
    SamCloseHandle(pv);
    v11 = v14 | 0x10000000;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v16 = 34;
LABEL_14:
      WPP_SF_d(v15[2], v16, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, v11);
    }
  }
LABEL_15:
  if ( v12 )
LABEL_16:
    CoTaskMemFree(v9);
  return v11;
}

```

## disassembly

```asm
0x180003660  mov     [rsp+pv], rcx
0x180003665  push    rbx
0x180003666  push    rbp
0x180003667  push    rsi
0x180003668  push    rdi
0x180003669  push    r12
0x18000366b  push    r13
0x18000366d  push    r14
0x18000366f  push    r15
0x180003671  sub     rsp, 58h
0x180003675  mov     r15, [rsp+98h+arg_20]
0x18000367d  xor     r13d, r13d
0x180003680  mov     [r9], r13
0x180003683  mov     r14, r9
0x180003686  mov     ebp, r8d
0x180003689  mov     r12d, edx
0x18000368c  mov     rdi, rcx
0x18000368f  mov     [r15], r13
0x180003692  test    rcx, rcx
0x180003695  jnz     short loc_1800036BC
0x180003697  lea     rcx, [rsp+98h+pv]
0x18000369f  call    CSGetAccountDomainSid
0x1800036a4  mov     rdi, [rsp+98h+pv]
0x1800036ac  mov     ebx, eax
0x1800036ae  mov     esi, 1
0x1800036b3  test    eax, eax
0x1800036b5  jns     short loc_1800036BF
0x1800036b7  jmp     loc_1800037B5
0x1800036bc  mov     esi, r13d
0x1800036bf  xorps   xmm0, xmm0
0x1800036c2  mov     [rsp+98h+var_78], 30h ; '0'
0x1800036cb  lea     r9, [rsp+98h+var_78]
0x1800036d0  mov     [rsp+98h+var_60], r13
0x1800036d5  mov     r8d, r12d
0x1800036d8  mov     [rsp+98h+pv], r13
0x1800036e0  lea     rdx, [rsp+98h+pv]
0x1800036e8  mov     [rsp+98h+var_70], r13
0x1800036ed  xor     ecx, ecx
0x1800036ef  mov     [rsp+98h+var_68], r13
0x1800036f4  movdqu  [rsp+98h+var_58], xmm0
0x1800036fa  call    cs:__imp_SamConnect
0x180003700  mov     ebx, eax
0x180003702  test    eax, eax
0x180003704  js      short loc_18000377C
0x180003706  mov     rcx, [rsp+98h+pv]
0x18000370e  lea     r9, [rsp+98h+arg_20]
0x180003716  mov     r8, rdi
0x180003719  mov     [rsp+98h+arg_20], r13
0x180003721  mov     edx, ebp
0x180003723  call    cs:__imp_SamOpenDomain
0x180003729  mov     ebx, eax
0x18000372b  test    eax, eax
0x18000372d  js      short loc_18000374A
0x18000372f  mov     rax, [rsp+98h+arg_20]
0x180003737  mov     ebx, r13d
0x18000373a  mov     [r15], rax
0x18000373d  mov     rax, [rsp+98h+pv]
0x180003745  mov     [r14], rax
0x180003748  jmp     short loc_1800037B1
0x18000374a  mov     rcx, [rsp+98h+pv]
0x180003752  call    cs:__imp_SamCloseHandle
0x180003758  bts     ebx, 1Ch
0x18000375c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003763  lea     rax, WPP_GLOBAL_Control
0x18000376a  cmp     rcx, rax
0x18000376d  jz      short loc_1800037B1
0x18000376f  test    byte ptr [rcx+1Ch], 2
0x180003773  jz      short loc_1800037B1
0x180003775  mov     edx, 22h ; '"'
0x18000377a  jmp     short loc_18000379E
0x18000377c  bts     ebx, 1Ch
0x180003780  mov     rcx, cs:WPP_GLOBAL_Control
0x180003787  lea     rax, WPP_GLOBAL_Control
0x18000378e  cmp     rcx, rax
0x180003791  jz      short loc_1800037B1
0x180003793  test    byte ptr [rcx+1Ch], 2
0x180003797  jz      short loc_1800037B1
0x180003799  mov     edx, 23h ; '#'
0x18000379e  mov     rcx, [rcx+10h]
0x1800037a2  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x1800037a9  mov     r9d, ebx
0x1800037ac  call    WPP_SF_d
0x1800037b1  test    esi, esi
0x1800037b3  jz      short loc_1800037BE
0x1800037b5  mov     rcx, rdi; pv
0x1800037b8  call    cs:__imp_CoTaskMemFree
0x1800037be  mov     eax, ebx
0x1800037c0  add     rsp, 58h
0x1800037c4  pop     r15
0x1800037c6  pop     r14
0x1800037c8  pop     r13
0x1800037ca  pop     r12
0x1800037cc  pop     rdi
0x1800037cd  pop     rsi
0x1800037ce  pop     rbp
0x1800037cf  pop     rbx
0x1800037d0  retn
```
