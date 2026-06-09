# HrGetCurrentCallLocality(CALL_LOCALITY *)

- ea: `0x180013230`
- end: `0x180013476`
- name: `?HrGetCurrentCallLocality@@YAJPEAW4CALL_LOCALITY@@@Z`
- size: `582`
- prototype: `__int64 __fastcall(enum CALL_LOCALITY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013180`

## callees

- `0x180013230`
- `0x18001347c`
- `0x180038ce4`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180013279`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180013279`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180013369`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180013369`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013350`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013350`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800132b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800132b5`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180013388`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180013388`

## pseudocode

```c
__int64 __fastcall HrGetCurrentCallLocality(enum CALL_LOCALITY *a1)
{
  int v2; // esi
  HRESULT Win32Error; // ebx
  STRSAFE_PCNZWCH v4; // rax
  HANDLE CurrentThread; // rax
  __int64 v7; // rdx
  WINBOOL IsMember; // [rsp+50h] [rbp+8h] BYREF
  void *ppInterface; // [rsp+58h] [rbp+10h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp+18h] BYREF

  hObject = 0;
  ppInterface = 0;
  if ( !a1 || !pSid )
    return 2147942487LL;
  v2 = 0;
  Win32Error = CoGetCallContext(&IID_IServerSecurity, &ppInterface);
  if ( Win32Error < 0 )
    goto LABEL_4;
  if ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface) )
  {
    Win32Error = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
    if ( Win32Error < 0 )
    {
LABEL_4:
      if ( Win32Error == -2147417833 )
      {
        *(_DWORD *)a1 = 1;
        Win32Error = 0;
        goto LABEL_6;
      }
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_7;
      v7 = 20;
LABEL_33:
      WPP_SF_d(*((_QWORD *)v4 + 2), v7, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids, (unsigned int)Win32Error);
      goto LABEL_6;
    }
    v2 = 1;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &hObject) )
  {
    Win32Error = HrFromLastWin32Error();
    if ( !Win32Error )
      goto LABEL_6;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_7;
    v7 = 19;
    goto LABEL_33;
  }
  IsMember = 0;
  if ( CheckTokenMembership(hObject, pSid, &IsMember) )
  {
    *(_DWORD *)a1 = (IsMember != 0) + 3;
    goto LABEL_6;
  }
  Win32Error = HrFromLastWin32Error();
  if ( Win32Error )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_7;
    v7 = 18;
    goto LABEL_33;
  }
LABEL_6:
  v4 = WPP_GLOBAL_Control;
LABEL_7:
  if ( hObject )
  {
    CloseHandle(hObject);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v2 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 40LL))(ppInterface);
    v4 = WPP_GLOBAL_Control;
  }
  if ( ppInterface )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
    v4 = WPP_GLOBAL_Control;
  }
  if ( Win32Error && v4 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v4[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v4 + 2), 21, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids, (unsigned int)Win32Error);
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x180013230  push    rbp
0x180013232  push    rdi
0x180013233  sub     rsp, 38h
0x180013237  xor     ebp, ebp
0x180013239  mov     rdi, rcx
0x18001323c  mov     [rsp+48h+hObject], rbp
0x180013241  mov     [rsp+48h+ppInterface], rbp
0x180013246  test    rcx, rcx
0x180013249  jz      loc_1800133C2
0x18001324f  cmp     cs:pSid, rbp
0x180013256  jz      loc_1800133C2
0x18001325c  mov     [rsp+48h+var_18], rbx
0x180013261  lea     rdx, [rsp+48h+ppInterface]; ppInterface
0x180013266  mov     [rsp+48h+var_20], rsi
0x18001326b  lea     rcx, IID_IServerSecurity; riid
0x180013272  mov     [rsp+48h+var_28], r14
0x180013277  mov     esi, ebp
0x180013279  call    cs:__imp_CoGetCallContext
0x18001327f  lea     r14, WPP_GLOBAL_Control
0x180013286  mov     ebx, eax
0x180013288  test    eax, eax
0x18001328a  jns     loc_18001331B
0x180013290  cmp     ebx, 80010117h
0x180013296  jnz     loc_18001340F
0x18001329c  mov     dword ptr [rdi], 1
0x1800132a2  mov     ebx, ebp
0x1800132a4  mov     rax, cs:WPP_GLOBAL_Control
0x1800132ab  mov     rcx, [rsp+48h+hObject]; hObject
0x1800132b0  test    rcx, rcx
0x1800132b3  jz      short loc_1800132C2
0x1800132b5  call    cs:__imp_CloseHandle
0x1800132bb  mov     rax, cs:WPP_GLOBAL_Control
0x1800132c2  test    esi, esi
0x1800132c4  mov     rsi, [rsp+48h+var_20]
0x1800132c9  jz      short loc_1800132E3
0x1800132cb  mov     rcx, [rsp+48h+ppInterface]
0x1800132d0  mov     rax, [rcx]
0x1800132d3  mov     rax, [rax+28h]
0x1800132d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132dc  mov     rax, cs:WPP_GLOBAL_Control
0x1800132e3  mov     rcx, [rsp+48h+ppInterface]
0x1800132e8  test    rcx, rcx
0x1800132eb  jz      short loc_180013300
0x1800132ed  mov     rax, [rcx]
0x1800132f0  mov     rax, [rax+10h]
0x1800132f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132f9  mov     rax, cs:WPP_GLOBAL_Control
0x180013300  test    ebx, ebx
0x180013302  jnz     loc_180013446
0x180013308  mov     r14, [rsp+48h+var_28]
0x18001330d  mov     eax, ebx
0x18001330f  mov     rbx, [rsp+48h+var_18]
0x180013314  add     rsp, 38h
0x180013318  pop     rdi
0x180013319  pop     rbp
0x18001331a  retn
0x18001331b  mov     rcx, [rsp+48h+ppInterface]
0x180013320  mov     rax, [rcx]
0x180013323  mov     rax, [rax+30h]
0x180013327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001332c  test    eax, eax
0x18001332e  jnz     short loc_180013350
0x180013330  mov     rcx, [rsp+48h+ppInterface]
0x180013335  mov     rax, [rcx]
0x180013338  mov     rax, [rax+20h]
0x18001333c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013341  mov     ebx, eax
0x180013343  test    eax, eax
0x180013345  js      loc_180013290
0x18001334b  mov     esi, 1
0x180013350  call    cs:__imp_GetCurrentThread
0x180013356  lea     r9, [rsp+48h+hObject]; TokenHandle
0x18001335b  mov     edx, 8; DesiredAccess
0x180013360  mov     rcx, rax; ThreadHandle
0x180013363  mov     r8d, 1; OpenAsSelf
0x180013369  call    cs:__imp_OpenThreadToken
0x18001336f  test    eax, eax
0x180013371  jz      short loc_1800133CC
0x180013373  mov     rdx, cs:pSid; SidToCheck
0x18001337a  lea     r8, [rsp+48h+IsMember]; IsMember
0x18001337f  mov     rcx, [rsp+48h+hObject]; TokenHandle
0x180013384  mov     [rsp+48h+IsMember], ebp
0x180013388  call    cs:__imp_CheckTokenMembership
0x18001338e  test    eax, eax
0x180013390  jnz     short loc_1800133FC
0x180013392  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180013397  mov     ebx, eax
0x180013399  test    eax, eax
0x18001339b  jz      loc_1800132A4
0x1800133a1  mov     rax, cs:WPP_GLOBAL_Control
0x1800133a8  cmp     rax, r14
0x1800133ab  jz      loc_1800132AB
0x1800133b1  test    byte ptr [rax+1Ch], 1
0x1800133b5  jz      loc_1800132AB
0x1800133bb  mov     edx, 12h
0x1800133c0  jmp     short loc_18001342E
0x1800133c2  mov     eax, 80070057h
0x1800133c7  jmp     loc_180013314
0x1800133cc  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800133d1  mov     ebx, eax
0x1800133d3  test    eax, eax
0x1800133d5  jz      loc_1800132A4
0x1800133db  mov     rax, cs:WPP_GLOBAL_Control
0x1800133e2  cmp     rax, r14
0x1800133e5  jz      loc_1800132AB
0x1800133eb  test    byte ptr [rax+1Ch], 1
0x1800133ef  jz      loc_1800132AB
0x1800133f5  mov     edx, 13h
0x1800133fa  jmp     short loc_18001342E
0x1800133fc  mov     eax, ebp
0x1800133fe  cmp     [rsp+48h+IsMember], eax
0x180013402  setnz   al
0x180013405  add     eax, 3
0x180013408  mov     [rdi], eax
0x18001340a  jmp     loc_1800132A4
0x18001340f  mov     rax, cs:WPP_GLOBAL_Control
0x180013416  cmp     rax, r14
0x180013419  jz      loc_1800132AB
0x18001341f  test    byte ptr [rax+1Ch], 1
0x180013423  jz      loc_1800132AB
0x180013429  mov     edx, 14h
0x18001342e  mov     rcx, [rax+10h]
0x180013432  lea     r8, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids
0x180013439  mov     r9d, ebx
0x18001343c  call    WPP_SF_d
0x180013441  jmp     loc_1800132A4
0x180013446  cmp     rax, r14
0x180013449  jz      loc_180013308
0x18001344f  test    byte ptr [rax+1Ch], 1
0x180013453  jz      loc_180013308
0x180013459  mov     rcx, [rax+10h]
0x18001345d  lea     r8, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids
0x180013464  mov     edx, 15h
0x180013469  mov     r9d, ebx
0x18001346c  call    WPP_SF_d
0x180013471  jmp     loc_180013308
```
