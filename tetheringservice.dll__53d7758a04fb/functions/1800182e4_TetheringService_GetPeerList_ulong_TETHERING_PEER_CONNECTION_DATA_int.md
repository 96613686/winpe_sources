# TetheringService::GetPeerList(ulong *,_TETHERING_PEER_CONNECTION_DATA * *,int)

- ea: `0x1800182e4`
- end: `0x1800186bc`
- name: `?GetPeerList@TetheringService@@QEAAJPEAKPEAPEAU_TETHERING_PEER_CONNECTION_DATA@@H@Z`
- size: `984`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, unsigned int *, struct _TETHERING_PEER_CONNECTION_DATA **, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000cbb0`
- `0x18001f740`

## callees

- `0x180002ffa`
- `0x18000bf74`
- `0x18000bfb4`
- `0x1800182e4`
- `0x18001c0dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018672`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018672`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800183fc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800183fc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180018514`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800185fa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180018514`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800185fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018660`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018660`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018345`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018345`

## pseudocode

```c
__int64 __fastcall TetheringService::GetPeerList(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned int *a2,
        struct _TETHERING_PEER_CONNECTION_DATA **a3,
        __int64 a4)
{
  int v4; // r14d
  unsigned int v8; // esi
  struct _RTL_CRITICAL_SECTION *v9; // r13
  struct _TETHERING_PEER_CONNECTION_DATA *v10; // rbp
  TetheringServiceTelemetry *v11; // rcx
  __int64 v12; // rdx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  unsigned int v14; // edi
  bool v15; // zf
  unsigned int v16; // eax
  __int64 v17; // rcx
  PRTL_CRITICAL_SECTION_DEBUG v18; // rbx
  unsigned int v19; // r14d
  char *v20; // rdx
  unsigned int v21; // r14d
  char *v22; // rdx

  v4 = a4;
  v8 = 0;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    LOBYTE(a4) = (_DWORD)a4 != 0;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 200, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, a4);
  }
  v9 = this + 34;
  v10 = 0;
  EnterCriticalSection(this + 34);
  TetheringService::ResetInactivityTimerIfNotSharing((TetheringService *)this);
  if ( !a2 || !a3 )
  {
    v8 = -2147024809;
    goto LABEL_44;
  }
  *a2 = 0;
  *a3 = 0;
  if ( !v4 || LODWORD(this[5].LockSemaphore) == 2 )
  {
    DebugInfo = this[35].DebugInfo;
    v14 = 0;
    if ( v4 )
    {
      while ( DebugInfo )
      {
        v15 = BYTE2(DebugInfo[4].EntryCount) == 0;
        v16 = v14 + 1;
        DebugInfo = *(PRTL_CRITICAL_SECTION_DEBUG *)&DebugInfo[4].Flags;
        if ( v15 )
          v16 = v14;
        v14 = v16;
      }
    }
    else
    {
      while ( DebugInfo )
      {
        DebugInfo = *(PRTL_CRITICAL_SECTION_DEBUG *)&DebugInfo[4].Flags;
        ++v14;
      }
    }
    v10 = (struct _TETHERING_PEER_CONNECTION_DATA *)malloc(226LL * v14);
    if ( v10 )
    {
      v18 = this[35].DebugInfo;
      if ( v4 )
      {
        v19 = 0;
        while ( v18 )
        {
          if ( BYTE2(v18[4].EntryCount) )
          {
            v20 = (char *)v10 + 226 * v19;
            if ( v20 )
            {
              *(_OWORD *)v20 = *(_OWORD *)&v18->Type;
              *((_OWORD *)v20 + 1) = v18->ProcessLocksList;
              *((_OWORD *)v20 + 2) = *(_OWORD *)&v18->EntryCount;
              *((_OWORD *)v20 + 3) = *(_OWORD *)&v18[1].Type;
              *((_OWORD *)v20 + 4) = v18[1].ProcessLocksList;
              *((_OWORD *)v20 + 5) = *(_OWORD *)&v18[1].EntryCount;
              *((_OWORD *)v20 + 6) = *(_OWORD *)&v18[2].Type;
              *((_OWORD *)v20 + 7) = v18[2].ProcessLocksList;
              *((_OWORD *)v20 + 8) = *(_OWORD *)&v18[2].EntryCount;
              *((_OWORD *)v20 + 9) = *(_OWORD *)&v18[3].Type;
              *((_OWORD *)v20 + 10) = v18[3].ProcessLocksList;
              *((_OWORD *)v20 + 11) = *(_OWORD *)&v18[3].EntryCount;
              *((_OWORD *)v20 + 12) = *(_OWORD *)&v18[4].Type;
              *((_OWORD *)v20 + 13) = v18[4].ProcessLocksList;
              *((_WORD *)v20 + 112) = v18[4].EntryCount;
            }
            else
            {
              *(_DWORD *)_o__errno(v17, 0) = 22;
              invalid_parameter_noinfo();
            }
            ++v19;
          }
          v18 = *(PRTL_CRITICAL_SECTION_DEBUG *)&v18[4].Flags;
        }
      }
      else
      {
        v21 = 0;
        while ( v18 )
        {
          v22 = (char *)v10 + 226 * v21;
          if ( v22 )
          {
            *(_OWORD *)v22 = *(_OWORD *)&v18->Type;
            *((_OWORD *)v22 + 1) = v18->ProcessLocksList;
            *((_OWORD *)v22 + 2) = *(_OWORD *)&v18->EntryCount;
            *((_OWORD *)v22 + 3) = *(_OWORD *)&v18[1].Type;
            *((_OWORD *)v22 + 4) = v18[1].ProcessLocksList;
            *((_OWORD *)v22 + 5) = *(_OWORD *)&v18[1].EntryCount;
            *((_OWORD *)v22 + 6) = *(_OWORD *)&v18[2].Type;
            *((_OWORD *)v22 + 7) = v18[2].ProcessLocksList;
            *((_OWORD *)v22 + 8) = *(_OWORD *)&v18[2].EntryCount;
            *((_OWORD *)v22 + 9) = *(_OWORD *)&v18[3].Type;
            *((_OWORD *)v22 + 10) = v18[3].ProcessLocksList;
            *((_OWORD *)v22 + 11) = *(_OWORD *)&v18[3].EntryCount;
            *((_OWORD *)v22 + 12) = *(_OWORD *)&v18[4].Type;
            *((_OWORD *)v22 + 13) = v18[4].ProcessLocksList;
            *((_WORD *)v22 + 112) = v18[4].EntryCount;
          }
          else
          {
            *(_DWORD *)_o__errno(v17, 0) = 22;
            invalid_parameter_noinfo();
          }
          v18 = *(PRTL_CRITICAL_SECTION_DEBUG *)&v18[4].Flags;
          ++v21;
        }
      }
      *a3 = v10;
      *a2 = v14;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 203, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v14);
      }
    }
    else
    {
      v8 = -2147024882;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 202;
        goto LABEL_11;
      }
    }
  }
  else
  {
    v8 = -2095972338;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 201;
LABEL_11:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v8);
    }
  }
LABEL_44:
  LeaveCriticalSection(v9);
  if ( (v8 & 0x80000000) != 0 && v10 )
    free(v10);
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 204, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x1800182e4  push    rbx
0x1800182e6  push    rbp
0x1800182e7  push    rsi
0x1800182e8  push    rdi
0x1800182e9  push    r12
0x1800182eb  push    r13
0x1800182ed  push    r14
0x1800182ef  push    r15
0x1800182f1  sub     rsp, 28h
0x1800182f5  mov     r14d, r9d
0x1800182f8  mov     r15, r8
0x1800182fb  mov     r12, rdx
0x1800182fe  mov     rbx, rcx
0x180018301  mov     rcx, cs:WPP_GLOBAL_Control
0x180018308  lea     rdi, WPP_GLOBAL_Control
0x18001830f  xor     esi, esi
0x180018311  cmp     rcx, rdi
0x180018314  jz      short loc_180018338
0x180018316  test    byte ptr [rcx+1Ch], 8
0x18001831a  jz      short loc_180018338
0x18001831c  mov     rcx, [rcx+10h]
0x180018320  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180018327  test    r9d, r9d
0x18001832a  mov     edx, 0C8h
0x18001832f  setnz   r9b
0x180018333  call    WPP_SF_c
0x180018338  lea     r13, [rbx+550h]
0x18001833f  mov     rbp, rsi
0x180018342  mov     rcx, r13; lpCriticalSection
0x180018345  call    cs:__imp_EnterCriticalSection
0x18001834b  mov     rcx, rbx; this
0x18001834e  call    ?ResetInactivityTimerIfNotSharing@TetheringService@@AEAAXXZ; TetheringService::ResetInactivityTimerIfNotSharing(void)
0x180018353  test    r12, r12
0x180018356  jz      loc_1800186B5
0x18001835c  test    r15, r15
0x18001835f  jz      loc_1800186B5
0x180018365  mov     [r12], esi
0x180018369  mov     [r15], rsi
0x18001836c  test    r14d, r14d
0x18001836f  jz      short loc_1800183B8
0x180018371  mov     eax, [rbx+0E0h]
0x180018377  cmp     eax, 2
0x18001837a  jz      short loc_1800183B8
0x18001837c  mov     esi, 8312000Eh
0x180018381  mov     rcx, cs:WPP_GLOBAL_Control
0x180018388  cmp     rcx, rdi
0x18001838b  jz      loc_18001865D
0x180018391  test    byte ptr [rcx+1Ch], 2
0x180018395  jz      loc_18001865D
0x18001839b  mov     edx, 0C9h
0x1800183a0  mov     rcx, [rcx+10h]
0x1800183a4  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x1800183ab  mov     r9d, esi
0x1800183ae  call    WPP_SF_d
0x1800183b3  jmp     loc_18001865D
0x1800183b8  mov     rcx, [rbx+578h]
0x1800183bf  mov     edi, esi
0x1800183c1  test    r14d, r14d
0x1800183c4  jz      short loc_1800183EE
0x1800183c6  jmp     short loc_1800183DE
0x1800183c8  cmp     [rcx+0E2h], sil
0x1800183cf  lea     eax, [rdi+1]
0x1800183d2  mov     rcx, [rcx+0E8h]
0x1800183d9  cmovz   eax, edi
0x1800183dc  mov     edi, eax
0x1800183de  test    rcx, rcx
0x1800183e1  jnz     short loc_1800183C8
0x1800183e3  jmp     short loc_1800183F3
0x1800183e5  mov     rcx, [rcx+0E8h]
0x1800183ec  inc     edi
0x1800183ee  test    rcx, rcx
0x1800183f1  jnz     short loc_1800183E5
0x1800183f3  mov     eax, edi
0x1800183f5  imul    rcx, rax, 0E2h; Size
0x1800183fc  call    cs:__imp_malloc
0x180018402  mov     rbp, rax
0x180018405  test    rax, rax
0x180018408  jnz     short loc_18001843A
0x18001840a  mov     esi, 8007000Eh
0x18001840f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018416  lea     rdi, WPP_GLOBAL_Control
0x18001841d  cmp     rcx, rdi
0x180018420  jz      loc_18001865D
0x180018426  test    byte ptr [rcx+1Ch], 1
0x18001842a  jz      loc_18001865D
0x180018430  mov     edx, 0CAh
0x180018435  jmp     loc_1800183A0
0x18001843a  mov     rbx, [rbx+578h]
0x180018441  test    r14d, r14d
0x180018444  jz      loc_18001853D
0x18001844a  xor     r14d, r14d
0x18001844d  jmp     loc_18001852F
0x180018452  cmp     [rbx+0E2h], sil
0x180018459  jz      loc_180018528
0x18001845f  mov     eax, r14d
0x180018462  imul    rdx, rax, 0E2h
0x180018469  add     rdx, rbp
0x18001846c  jz      loc_180018514
0x180018472  movups  xmm0, xmmword ptr [rbx]
0x180018475  movups  xmmword ptr [rdx], xmm0
0x180018478  movups  xmm1, xmmword ptr [rbx+10h]
0x18001847c  movups  xmmword ptr [rdx+10h], xmm1
0x180018480  movups  xmm0, xmmword ptr [rbx+20h]
0x180018484  movups  xmmword ptr [rdx+20h], xmm0
0x180018488  movups  xmm1, xmmword ptr [rbx+30h]
0x18001848c  movups  xmmword ptr [rdx+30h], xmm1
0x180018490  movups  xmm0, xmmword ptr [rbx+40h]
0x180018494  movups  xmmword ptr [rdx+40h], xmm0
0x180018498  movups  xmm1, xmmword ptr [rbx+50h]
0x18001849c  movups  xmmword ptr [rdx+50h], xmm1
0x1800184a0  movups  xmm0, xmmword ptr [rbx+60h]
0x1800184a4  movups  xmmword ptr [rdx+60h], xmm0
0x1800184a8  movups  xmm1, xmmword ptr [rbx+70h]
0x1800184ac  movups  xmmword ptr [rdx+70h], xmm1
0x1800184b0  movups  xmm0, xmmword ptr [rbx+80h]
0x1800184b7  movups  xmmword ptr [rdx+80h], xmm0
0x1800184be  movups  xmm1, xmmword ptr [rbx+90h]
0x1800184c5  movups  xmmword ptr [rdx+90h], xmm1
0x1800184cc  movups  xmm0, xmmword ptr [rbx+0A0h]
0x1800184d3  movups  xmmword ptr [rdx+0A0h], xmm0
0x1800184da  movups  xmm1, xmmword ptr [rbx+0B0h]
0x1800184e1  movups  xmmword ptr [rdx+0B0h], xmm1
0x1800184e8  movups  xmm0, xmmword ptr [rbx+0C0h]
0x1800184ef  movups  xmmword ptr [rdx+0C0h], xmm0
0x1800184f6  movups  xmm1, xmmword ptr [rbx+0D0h]
0x1800184fd  movups  xmmword ptr [rdx+0D0h], xmm1
0x180018504  movzx   eax, word ptr [rbx+0E0h]
0x18001850b  mov     [rdx+0E0h], ax
0x180018512  jmp     short loc_180018525
0x180018514  call    cs:__imp__o__errno
0x18001851a  mov     dword ptr [rax], 16h
0x180018520  call    _invalid_parameter_noinfo
0x180018525  inc     r14d
0x180018528  mov     rbx, [rbx+0E8h]
0x18001852f  test    rbx, rbx
0x180018532  jnz     loc_180018452
0x180018538  jmp     loc_18001861E
0x18001853d  xor     r14d, r14d
0x180018540  jmp     loc_180018615
0x180018545  mov     eax, r14d
0x180018548  imul    rdx, rax, 0E2h
0x18001854f  add     rdx, rbp
0x180018552  jz      loc_1800185FA
0x180018558  movups  xmm0, xmmword ptr [rbx]
0x18001855b  movups  xmmword ptr [rdx], xmm0
0x18001855e  movups  xmm1, xmmword ptr [rbx+10h]
0x180018562  movups  xmmword ptr [rdx+10h], xmm1
0x180018566  movups  xmm0, xmmword ptr [rbx+20h]
0x18001856a  movups  xmmword ptr [rdx+20h], xmm0
0x18001856e  movups  xmm1, xmmword ptr [rbx+30h]
0x180018572  movups  xmmword ptr [rdx+30h], xmm1
0x180018576  movups  xmm0, xmmword ptr [rbx+40h]
0x18001857a  movups  xmmword ptr [rdx+40h], xmm0
0x18001857e  movups  xmm1, xmmword ptr [rbx+50h]
0x180018582  movups  xmmword ptr [rdx+50h], xmm1
0x180018586  movups  xmm0, xmmword ptr [rbx+60h]
0x18001858a  movups  xmmword ptr [rdx+60h], xmm0
0x18001858e  movups  xmm1, xmmword ptr [rbx+70h]
0x180018592  movups  xmmword ptr [rdx+70h], xmm1
0x180018596  movups  xmm0, xmmword ptr [rbx+80h]
0x18001859d  movups  xmmword ptr [rdx+80h], xmm0
0x1800185a4  movups  xmm1, xmmword ptr [rbx+90h]
0x1800185ab  movups  xmmword ptr [rdx+90h], xmm1
0x1800185b2  movups  xmm0, xmmword ptr [rbx+0A0h]
0x1800185b9  movups  xmmword ptr [rdx+0A0h], xmm0
0x1800185c0  movups  xmm1, xmmword ptr [rbx+0B0h]
0x1800185c7  movups  xmmword ptr [rdx+0B0h], xmm1
0x1800185ce  movups  xmm0, xmmword ptr [rbx+0C0h]
0x1800185d5  movups  xmmword ptr [rdx+0C0h], xmm0
0x1800185dc  movups  xmm1, xmmword ptr [rbx+0D0h]
0x1800185e3  movups  xmmword ptr [rdx+0D0h], xmm1
0x1800185ea  movzx   eax, word ptr [rbx+0E0h]
0x1800185f1  mov     [rdx+0E0h], ax
0x1800185f8  jmp     short loc_18001860B
0x1800185fa  call    cs:__imp__o__errno
0x180018600  mov     dword ptr [rax], 16h
0x180018606  call    _invalid_parameter_noinfo
0x18001860b  mov     rbx, [rbx+0E8h]
0x180018612  inc     r14d
0x180018615  test    rbx, rbx
0x180018618  jnz     loc_180018545
0x18001861e  mov     [r15], rbp
0x180018621  mov     [r12], edi
0x180018625  mov     rcx, cs:WPP_GLOBAL_Control
0x18001862c  lea     rax, WPP_GLOBAL_Control
0x180018633  cmp     rcx, rax
0x180018636  jz      short loc_180018656
0x180018638  test    byte ptr [rcx+1Ch], 4
0x18001863c  jz      short loc_180018656
0x18001863e  mov     rcx, [rcx+10h]
0x180018642  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180018649  mov     edx, 0CBh
0x18001864e  mov     r9d, edi
0x180018651  call    WPP_SF_d
0x180018656  lea     rdi, WPP_GLOBAL_Control
0x18001865d  mov     rcx, r13; lpCriticalSection
0x180018660  call    cs:__imp_LeaveCriticalSection
0x180018666  test    esi, esi
0x180018668  jns     short loc_180018678
0x18001866a  test    rbp, rbp
0x18001866d  jz      short loc_180018678
0x18001866f  mov     rcx, rbp; Block
0x180018672  call    cs:__imp_free
0x180018678  mov     rcx, cs:WPP_GLOBAL_Control
0x18001867f  cmp     rcx, rdi
0x180018682  jz      short loc_1800186A2
0x180018684  test    byte ptr [rcx+1Ch], 8
0x180018688  jz      short loc_1800186A2
0x18001868a  mov     rcx, [rcx+10h]
0x18001868e  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180018695  mov     edx, 0CCh
0x18001869a  mov     r9d, esi
0x18001869d  call    WPP_SF_d
0x1800186a2  mov     eax, esi
0x1800186a4  add     rsp, 28h
0x1800186a8  pop     r15
0x1800186aa  pop     r14
0x1800186ac  pop     r13
0x1800186ae  pop     r12
0x1800186b0  pop     rdi
0x1800186b1  pop     rsi
0x1800186b2  pop     rbp
0x1800186b3  pop     rbx
0x1800186b4  retn
0x1800186b5  mov     esi, 80070057h
0x1800186ba  jmp     short loc_18001865D
```
