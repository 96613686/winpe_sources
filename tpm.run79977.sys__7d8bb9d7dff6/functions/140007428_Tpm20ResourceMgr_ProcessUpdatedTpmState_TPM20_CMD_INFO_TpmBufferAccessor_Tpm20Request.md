# Tpm20ResourceMgr::ProcessUpdatedTpmState(_TPM20_CMD_INFO,TpmBufferAccessor *,Tpm20Request *)

- ea: `0x140007428`
- end: `0x14000759d`
- name: `?ProcessUpdatedTpmState@Tpm20ResourceMgr@@AEAAJT_TPM20_CMD_INFO@@PEAVTpmBufferAccessor@@PEAVTpm20Request@@@Z`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140016afc`

## callees

- `0x140007428`
- `0x1400075a4`
- `0x1400078b8`
- `0x140008fec`

## pseudocode

```c
__int64 __fastcall Tpm20ResourceMgr::ProcessUpdatedTpmState(Tpm20ResourceMgr *a1, int a2, _DWORD *a3, __int64 a4)
{
  __int64 v8; // rdx
  __int64 v9; // r10
  __int64 v10; // r9
  signed int i; // edx
  __int64 v12; // rcx
  __int64 v13; // rax
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  __int64 j; // rsi
  struct Tpm20Resource *v17; // r8
  unsigned int v18; // [rsp+58h] [rbp+10h]

  v18 = 0;
  if ( (a2 & 0x10000000) == 0 )
    goto LABEL_2;
  v8 = (unsigned int)(a3[4] - *a3);
  if ( (int)v8 + 4 < (unsigned int)v8 || (v9 = (unsigned int)v8, v8 + 4 > (unsigned __int64)(unsigned int)a3[2]) )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return 3221225862LL;
    v15 = 41;
    goto LABEL_16;
  }
  v10 = *(_QWORD *)a3;
  for ( i = 0; (unsigned int)i < 4; ++i )
  {
    v12 = i;
    v13 = v9 - i;
    *((_BYTE *)&v18 + v12) = *(_BYTE *)(v13 + v10 + 3);
  }
  *((_QWORD *)a3 + 2) += 4LL;
  if ( (int)Tpm20ResourceMgr::ActivateResource(a1, *(_QWORD *)(a4 + 16), *(_QWORD *)(a4 + 168), v18) < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return 3221225862LL;
    v15 = 42;
LABEL_16:
    WPP_SF_(v14->AttachedDevice, v15, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids);
    return 3221225862LL;
  }
  *(_QWORD *)(a4 + 168) = 0;
LABEL_2:
  if ( (a2 & 0x1000000) != 0 )
  {
    for ( j = 0; (unsigned int)j < *(_DWORD *)(a4 + 196); j = (unsigned int)(j + 1) )
    {
      v17 = *(struct Tpm20Resource **)(a4 + 8 * j + 48);
      if ( *((_DWORD *)v17 + 14) == 2 )
        Tpm20ResourceMgr::RemovedLoadedResource(a1, *(const struct Tpm20Context **)(a4 + 16), v17);
    }
  }
  if ( (_WORD)a2 == 357 && (a2 & 0x20000000) == 0 )
    Tpm20ResourceMgr::RemovedLoadedResource(
      a1,
      *(const struct Tpm20Context **)(a4 + 16),
      *(struct Tpm20Resource **)(a4 + 48));
  if ( (a2 & 0x800000) != 0 )
    *((_BYTE *)a1 + 169) = 1;
  return 0;
}

```

## disassembly

```asm
0x140007428  push    rbx
0x14000742a  push    rbp
0x14000742b  push    rsi
0x14000742c  push    rdi
0x14000742d  sub     rsp, 28h
0x140007431  mov     [rsp+48h+arg_8], 0
0x140007439  mov     rdi, r9
0x14000743c  mov     ebx, edx
0x14000743e  mov     rbp, rcx
0x140007441  bt      edx, 1Ch
0x140007445  jb      short loc_140007472
0x140007447  bt      ebx, 18h
0x14000744b  jb      loc_14000754F
0x140007451  cmp     bx, 165h
0x140007456  jz      loc_140007581
0x14000745c  bt      ebx, 17h
0x140007460  jb      loc_1400074E7
0x140007466  xor     eax, eax
0x140007468  add     rsp, 28h
0x14000746c  pop     rdi
0x14000746d  pop     rsi
0x14000746e  pop     rbp
0x14000746f  pop     rbx
0x140007470  retn
0x140007472  mov     edx, [r8+10h]
0x140007476  sub     edx, [r8]
0x140007479  lea     eax, [rdx+4]
0x14000747c  cmp     eax, edx
0x14000747e  jb      loc_140007524
0x140007484  mov     ecx, [r8+8]
0x140007488  lea     rax, [rdx+4]
0x14000748c  mov     r10d, edx
0x14000748f  cmp     rax, rcx
0x140007492  ja      loc_140007524
0x140007498  mov     r9, [r8]
0x14000749b  xor     edx, edx
0x14000749d  movsxd  rcx, edx
0x1400074a0  mov     rax, r10
0x1400074a3  sub     rax, rcx
0x1400074a6  inc     edx
0x1400074a8  mov     al, [rax+r9+3]
0x1400074ad  mov     byte ptr [rsp+rcx+48h+arg_8], al
0x1400074b1  cmp     edx, 4
0x1400074b4  jb      short loc_14000749D
0x1400074b6  add     qword ptr [r8+10h], 4
0x1400074bb  mov     r9d, [rsp+48h+arg_8]
0x1400074c0  mov     rcx, rbp
0x1400074c3  mov     r8, [rdi+0A8h]
0x1400074ca  mov     rdx, [rdi+10h]
0x1400074ce  call    ?ActivateResource@Tpm20ResourceMgr@@AEAAJPEAVTpm20Context@@PEAVTpm20Resource@@T_TPM20_HANDLE@@@Z; Tpm20ResourceMgr::ActivateResource(Tpm20Context *,Tpm20Resource *,_TPM20_HANDLE)
0x1400074d3  test    eax, eax
0x1400074d5  js      short loc_1400074F3
0x1400074d7  mov     qword ptr [rdi+0A8h], 0
0x1400074e2  jmp     loc_140007447
0x1400074e7  mov     byte ptr [rbp+0A9h], 1
0x1400074ee  jmp     loc_140007466
0x1400074f3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400074fa  lea     rax, WPP_GLOBAL_Control
0x140007501  cmp     rcx, rax
0x140007504  jz      short loc_140007537
0x140007506  mov     eax, [rcx+2Ch]
0x140007509  test    al, 1
0x14000750b  jz      short loc_140007537
0x14000750d  mov     edx, 2Ah ; '*'
0x140007512  mov     rcx, [rcx+18h]
0x140007516  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x14000751d  call    WPP_SF_
0x140007522  jmp     short loc_140007537
0x140007524  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000752b  lea     rax, WPP_GLOBAL_Control
0x140007532  cmp     rcx, rax
0x140007535  jnz     short loc_140007541
0x140007537  mov     eax, 0C0000186h
0x14000753c  jmp     loc_140007468
0x140007541  mov     eax, [rcx+2Ch]
0x140007544  test    al, 1
0x140007546  jz      short loc_140007537
0x140007548  mov     edx, 29h ; ')'
0x14000754d  jmp     short loc_140007512
0x14000754f  xor     esi, esi
0x140007551  cmp     [rdi+0C4h], esi
0x140007557  jbe     loc_140007451
0x14000755d  mov     r8, [rdi+rsi*8+30h]; struct Tpm20Resource *
0x140007562  cmp     dword ptr [r8+38h], 2
0x140007567  jnz     short loc_140007572
0x140007569  mov     rdx, [rdi+10h]; struct Tpm20Context *
0x14000756d  call    ?RemovedLoadedResource@Tpm20ResourceMgr@@AEAAXPEBVTpm20Context@@PEAVTpm20Resource@@@Z; Tpm20ResourceMgr::RemovedLoadedResource(Tpm20Context const *,Tpm20Resource *)
0x140007572  inc     esi
0x140007574  cmp     esi, [rdi+0C4h]
0x14000757a  jb      short loc_14000755D
0x14000757c  jmp     loc_140007451
0x140007581  bt      ebx, 1Dh
0x140007585  jb      loc_14000745C
0x14000758b  mov     r8, [rdi+30h]; struct Tpm20Resource *
0x14000758f  mov     rdx, [rdi+10h]; struct Tpm20Context *
0x140007593  call    ?RemovedLoadedResource@Tpm20ResourceMgr@@AEAAXPEBVTpm20Context@@PEAVTpm20Resource@@@Z; Tpm20ResourceMgr::RemovedLoadedResource(Tpm20Context const *,Tpm20Resource *)
0x140007598  jmp     loc_14000745C
```
