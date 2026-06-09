# UbpmpRunSerializedActionCallback(void *,uchar,void *)

- ea: `0x180019a30`
- end: `0x180019d7e`
- name: `?UbpmpRunSerializedActionCallback@@YAXPEAXE0@Z`
- size: `846`
- prototype: `void __fastcall(void *, unsigned __int8, void *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180007c50`
- `0x180007e30`
- `0x180009c20`
- `0x18000a500`
- `0x18000aac0`
- `0x18000d200`
- `0x180018254`
- `0x180018538`
- `0x180019a30`
- `0x180019d90`
- `0x180024df0`
- `0x180030cec`
- `0x18003508c`
- `0x180035ec4`
- `0x18003d7de`
- `0x18003d810`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019c96`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019c96`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180019ac6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180019ac6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180019ada`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180019ada`

## pseudocode

```c
void __fastcall UbpmpRunSerializedActionCallback(char *a1, char a2, void *a3)
{
  unsigned __int16 v3; // r14
  int v6; // eax
  DWORD v7; // ebx
  int v8; // esi
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v9; // rbx
  signed __int32 v10; // ecx
  int v11; // r8d
  void *v12; // rcx
  int v13; // ecx
  __int64 v14; // rax
  __int64 v15; // rdx
  int v16; // [rsp+20h] [rbp-E0h]
  struct _UBPM_TRIGGER_CONSUMER_BLOCK *v17; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[4]; // [rsp+70h] [rbp-90h] BYREF
  int v19; // [rsp+74h] [rbp-8Ch]
  int v20; // [rsp+78h] [rbp-88h]
  DWORD LengthSid; // [rsp+80h] [rbp-80h]
  __int64 v22; // [rsp+88h] [rbp-78h]
  char v23; // [rsp+98h] [rbp-68h]
  __int64 v24; // [rsp+A0h] [rbp-60h]
  char v25; // [rsp+A8h] [rbp-58h]
  __int64 v26; // [rsp+B0h] [rbp-50h]
  _BYTE v27[144]; // [rsp+C0h] [rbp-40h] BYREF

  v3 = 0;
  v17 = 0;
  if ( *((_WORD *)a1 + 10) != 1 )
    v3 = *((_WORD *)a1 + 10);
  memset_0(v18, 0, 0x48u);
  if ( (a2 & 4) == 0 )
  {
    memset_0(v27, 0, 0x88u);
    UbpmUtilsStartLockTracking((struct _CEM_LOCK_TRACKER *)v27);
    v6 = UbpmpOpenTriggerConsumer((UUID *)(a1 + 24), 0, &v17);
    v7 = UbpmpLockTrackerId;
    v8 = v6;
    if ( UbpmpLockTrackerId != -1 )
    {
      if ( *(_QWORD *)TlsGetValue(UbpmpLockTrackerId) )
        __int2c();
      TlsSetValue(v7, 0);
    }
    v9 = v17;
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          82,
          WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
          *((unsigned __int16 *)a1 + 10),
          v8);
    }
    else
    {
      v10 = *((_DWORD *)a1 + 10);
      if ( v10 == _InterlockedCompareExchange((volatile signed __int32 *)v17 + 11, v10, v10) )
      {
        if ( !(unsigned int)UbpmConsumerIncPendingActions((__int64)v9) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            WPP_SF_SddiL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)WPP_GLOBAL_Control,
              v11,
              *(_QWORD *)(*((_QWORD *)v9 + 3) + 8LL),
              *((_WORD *)a1 + 10),
              *((_DWORD *)a1 + 10),
              *((_QWORD *)a1 + 9),
              *((_DWORD *)a1 + 25));
          if ( *((_WORD *)a1 + 10) == 1 )
          {
            if ( !(unsigned __int8)UbpmCheckAndMarkOneActiveTask((UUID *)(a1 + 4)) )
              UbpmRunConsumerQueuedActions(v9, 0, 0);
          }
          else
          {
            v12 = (void *)*((_QWORD *)a1 + 8);
            v20 = *((_DWORD *)a1 + 14);
            if ( v12 )
              LengthSid = GetLengthSid(v12);
            else
              LengthSid = 0;
            v13 = *((_DWORD *)a1 + 25);
            v22 = *((_QWORD *)a1 + 8);
            v23 = a1[104];
            v24 = *((_QWORD *)a1 + 14);
            v25 = a1[120];
            v26 = *((_QWORD *)a1 + 16);
            v19 = v13;
            v14 = *(_QWORD *)(*((_QWORD *)v9 + 3) + 40LL);
            if ( *(_DWORD *)(v14 + 40LL * v3 - 24) == 1 )
            {
              v15 = *(_QWORD *)(*(_QWORD *)(v14 + 40LL * v3 - 16) + 32LL);
              if ( v15 )
              {
                if ( *(_DWORD *)(v15 + 32) == 2 )
                  v19 = v13 | 6;
              }
            }
            UbpmRunConsumerActions(
              v9,
              v16,
              *((_QWORD *)a1 + 9),
              *((_DWORD *)a1 + 20),
              *((_DWORD *)a1 + 21),
              *((_QWORD *)a1 + 11),
              (struct _UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *)v18,
              0);
          }
          UbpmConsumerDecPendingActions((__int64)v9);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Sddd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          83,
          (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
          *(_QWORD *)(*((_QWORD *)v9 + 3) + 8LL),
          211,
          *((_DWORD *)v9 + 11),
          *((_DWORD *)a1 + 10));
      }
    }
    if ( v9 )
      UbpmCloseTriggerConsumer(v9);
  }
  if ( (a1[96] & 1) != 0 )
    UbpmpRemoveQueuedSerialActions((UUID *)(a1 + 4), 0, 0, 0, v3);
  UBPM_MIDL_user_free(*((_QWORD *)a1 + 14));
  UBPM_MIDL_user_free(*((_QWORD *)a1 + 16));
  UBPM_MIDL_user_free(*((_QWORD *)a1 + 11));
  UBPM_MIDL_user_free(a1);
}

```

## disassembly

```asm
0x180019a30  push    rbp
0x180019a32  push    rbx
0x180019a33  push    rsi
0x180019a34  push    rdi
0x180019a35  push    r12
0x180019a37  push    r14
0x180019a39  lea     rbp, [rsp-68h]
0x180019a3e  sub     rsp, 168h
0x180019a45  mov     rax, cs:__security_cookie
0x180019a4c  xor     rax, rsp
0x180019a4f  mov     [rbp+90h+var_40], rax
0x180019a53  xor     r14d, r14d
0x180019a56  mov     [rsp+190h+var_130], 0
0x180019a5f  mov     bl, dl
0x180019a61  mov     rdi, rcx
0x180019a64  lea     r12d, [r14+1]
0x180019a68  cmp     [rcx+14h], r12w
0x180019a6d  lea     r8d, [r12+47h]; Size
0x180019a72  cmovnz  r14w, [rcx+14h]
0x180019a78  xor     edx, edx; Val
0x180019a7a  lea     rcx, [rsp+190h+var_120]; void *
0x180019a7f  call    memset_0
0x180019a84  test    bl, 4
0x180019a87  jnz     loc_180019B6B
0x180019a8d  xor     edx, edx; Val
0x180019a8f  lea     rcx, [rbp+90h+var_D0]; void *
0x180019a93  mov     r8d, 88h; Size
0x180019a99  call    memset_0
0x180019a9e  lea     rcx, [rbp+90h+var_D0]; lpTlsValue
0x180019aa2  call    ?UbpmUtilsStartLockTracking@@YAXPEAU_CEM_LOCK_TRACKER@@@Z; UbpmUtilsStartLockTracking(_CEM_LOCK_TRACKER *)
0x180019aa7  lea     rcx, [rdi+18h]; Uuid2
0x180019aab  xor     edx, edx; String2
0x180019aad  lea     r8, [rsp+190h+var_130]
0x180019ab2  call    UbpmpOpenTriggerConsumer
0x180019ab7  mov     ebx, cs:UbpmpLockTrackerId
0x180019abd  mov     esi, eax
0x180019abf  cmp     ebx, 0FFFFFFFFh
0x180019ac2  jz      short loc_180019AE0
0x180019ac4  mov     ecx, ebx; dwTlsIndex
0x180019ac6  call    cs:__imp_TlsGetValue
0x180019acc  cmp     qword ptr [rax], 0
0x180019ad0  jnz     loc_180019BF3
0x180019ad6  xor     edx, edx; lpTlsValue
0x180019ad8  mov     ecx, ebx; dwTlsIndex
0x180019ada  call    cs:__imp_TlsSetValue
0x180019ae0  mov     rbx, [rsp+190h+var_130]
0x180019ae5  test    esi, esi
0x180019ae7  jnz     loc_180019BB7
0x180019aed  mov     ecx, [rdi+28h]
0x180019af0  mov     eax, ecx
0x180019af2  lock cmpxchg [rbx+2Ch], ecx
0x180019af7  mov     r8d, [rdi+28h]
0x180019afb  jnz     loc_180019BFA
0x180019b01  mov     rcx, rbx
0x180019b04  call    UbpmConsumerIncPendingActions
0x180019b09  test    eax, eax
0x180019b0b  jnz     short loc_180019B5E
0x180019b0d  mov     rdx, cs:WPP_GLOBAL_Control
0x180019b14  lea     rax, WPP_GLOBAL_Control
0x180019b1b  cmp     rdx, rax
0x180019b1e  jz      short loc_180019B2D
0x180019b20  test    dword ptr [rdx+1Ch], 200h
0x180019b27  jnz     loc_180019C51
0x180019b2d  movzx   r8d, word ptr [rdi+14h]
0x180019b32  cmp     r8w, r12w
0x180019b36  jnz     loc_180019C86
0x180019b3c  lea     rcx, [rdi+4]; Uuid2
0x180019b40  call    UbpmCheckAndMarkOneActiveTask
0x180019b45  test    al, al
0x180019b47  jnz     short loc_180019B56
0x180019b49  xor     r8d, r8d
0x180019b4c  xor     edx, edx
0x180019b4e  mov     rcx, rbx
0x180019b51  call    UbpmRunConsumerQueuedActions
0x180019b56  mov     rcx, rbx
0x180019b59  call    UbpmConsumerDecPendingActions
0x180019b5e  test    rbx, rbx
0x180019b61  jz      short loc_180019B6B
0x180019b63  mov     rcx, rbx
0x180019b66  call    UbpmCloseTriggerConsumer
0x180019b6b  test    [rdi+60h], r12b
0x180019b6f  jnz     loc_180019D62
0x180019b75  mov     rcx, [rdi+70h]
0x180019b79  call    UBPM_MIDL_user_free
0x180019b7e  mov     rcx, [rdi+80h]
0x180019b85  call    UBPM_MIDL_user_free
0x180019b8a  mov     rcx, [rdi+58h]
0x180019b8e  call    UBPM_MIDL_user_free
0x180019b93  mov     rcx, rdi
0x180019b96  call    UBPM_MIDL_user_free
0x180019b9b  mov     rcx, [rbp+90h+var_40]
0x180019b9f  xor     rcx, rsp; StackCookie
0x180019ba2  call    __security_check_cookie
0x180019ba7  add     rsp, 168h
0x180019bae  pop     r14
0x180019bb0  pop     r12
0x180019bb2  pop     rdi
0x180019bb3  pop     rsi
0x180019bb4  pop     rbx
0x180019bb5  pop     rbp
0x180019bb6  retn
0x180019bb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180019bbe  lea     rax, WPP_GLOBAL_Control
0x180019bc5  cmp     rcx, rax
0x180019bc8  jz      short loc_180019B5E
0x180019bca  test    [rcx+1Ch], r12b
0x180019bce  jz      short loc_180019B5E
0x180019bd0  movzx   r9d, word ptr [rdi+14h]
0x180019bd5  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x180019bdc  mov     rcx, [rcx+10h]
0x180019be0  mov     edx, 52h ; 'R'
0x180019be5  mov     dword ptr [rsp+190h+var_170], esi
0x180019be9  call    WPP_SF_dd
0x180019bee  jmp     loc_180019B5E
0x180019bf3  int     2Ch; Windows NT - assertion failure
0x180019bf5  jmp     loc_180019AD6
0x180019bfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c01  lea     rax, WPP_GLOBAL_Control
0x180019c08  cmp     rcx, rax
0x180019c0b  jz      loc_180019B5E
0x180019c11  test    [rcx+1Ch], r12b
0x180019c15  jz      loc_180019B5E
0x180019c1b  mov     rax, [rbx+18h]
0x180019c1f  mov     edx, 53h ; 'S'
0x180019c24  mov     rcx, [rcx+10h]
0x180019c28  mov     [rsp+190h+var_160], r8d
0x180019c2d  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x180019c34  mov     r9, [rax+8]
0x180019c38  mov     eax, [rbx+2Ch]
0x180019c3b  mov     dword ptr [rsp+190h+var_168], eax
0x180019c3f  mov     dword ptr [rsp+190h+var_170], 4D3h
0x180019c47  call    WPP_SF_Sddd
0x180019c4c  jmp     loc_180019B5E
0x180019c51  mov     eax, [rdi+64h]
0x180019c54  movzx   ecx, word ptr [rdi+14h]
0x180019c58  mov     r9, [rbx+18h]
0x180019c5c  mov     [rsp+190h+var_158], eax
0x180019c60  mov     rax, [rdi+48h]
0x180019c64  mov     qword ptr [rsp+190h+var_160], rax
0x180019c69  mov     eax, [rdi+28h]
0x180019c6c  mov     r9, [r9+8]
0x180019c70  mov     dword ptr [rsp+190h+var_168], eax
0x180019c74  mov     dword ptr [rsp+190h+var_170], ecx
0x180019c78  mov     rcx, [rdx+10h]
0x180019c7c  call    WPP_SF_SddiL
0x180019c81  jmp     loc_180019B2D
0x180019c86  mov     rcx, [rdi+40h]; pSid
0x180019c8a  mov     eax, [rdi+38h]
0x180019c8d  mov     [rsp+190h+var_118], eax
0x180019c91  test    rcx, rcx
0x180019c94  jz      short loc_180019CA6
0x180019c96  call    cs:__imp_GetLengthSid
0x180019c9c  movzx   r8d, word ptr [rdi+14h]
0x180019ca1  mov     [rbp+90h+var_110], eax
0x180019ca4  jmp     short loc_180019CAD
0x180019ca6  mov     [rbp+90h+var_110], 0
0x180019cad  mov     rax, [rdi+40h]
0x180019cb1  mov     ecx, [rdi+64h]
0x180019cb4  mov     [rbp+90h+var_108], rax
0x180019cb8  mov     al, [rdi+68h]
0x180019cbb  mov     [rbp+90h+var_F8], al
0x180019cbe  mov     rax, [rdi+70h]
0x180019cc2  mov     [rbp+90h+var_F0], rax
0x180019cc6  mov     al, [rdi+78h]
0x180019cc9  mov     [rbp+90h+var_E8], al
0x180019ccc  mov     rax, [rdi+80h]
0x180019cd3  mov     [rbp+90h+var_E0], rax
0x180019cd7  mov     [rsp+190h+var_11C], ecx
0x180019cdb  movzx   eax, r14w
0x180019cdf  lea     rdx, [rax+rax*4]
0x180019ce3  mov     rax, [rbx+18h]
0x180019ce7  mov     rax, [rax+28h]
0x180019ceb  cmp     [rax+rdx*8-18h], r12d
0x180019cf0  jnz     short loc_180019D0D
0x180019cf2  mov     rax, [rax+rdx*8-10h]
0x180019cf7  mov     rdx, [rax+20h]
0x180019cfb  test    rdx, rdx
0x180019cfe  jz      short loc_180019D0D
0x180019d00  cmp     dword ptr [rdx+20h], 2
0x180019d04  jnz     short loc_180019D0D
0x180019d06  or      ecx, 6
0x180019d09  mov     [rsp+190h+var_11C], ecx
0x180019d0d  mov     [rsp+190h+var_140], 0; __int64
0x180019d16  lea     rax, [rsp+190h+var_120]
0x180019d1b  mov     [rsp+190h+var_148], rax; struct _UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *
0x180019d20  lea     r9, [rdi+4]
0x180019d24  mov     rax, [rdi+58h]
0x180019d28  mov     rdx, r12
0x180019d2b  mov     [rsp+190h+var_150], rax; __int64
0x180019d30  mov     eax, [rdi+54h]
0x180019d33  mov     [rsp+190h+var_158], eax; unsigned int
0x180019d37  mov     eax, [rdi+50h]
0x180019d3a  movzx   ecx, r8w
0x180019d3e  mov     r8, [rdi+30h]
0x180019d42  sub     ecx, r12d
0x180019d45  mov     [rsp+190h+var_160], eax; unsigned int
0x180019d49  mov     rax, [rdi+48h]
0x180019d4d  shl     rdx, cl
0x180019d50  mov     rcx, rbx; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x180019d53  mov     [rsp+190h+var_168], rax; unsigned __int64
0x180019d58  call    UbpmRunConsumerActions
0x180019d5d  jmp     loc_180019B56
0x180019d62  lea     rcx, [rdi+4]; Uuid1
0x180019d66  mov     [rsp+190h+var_170], r14w; __int16
0x180019d6c  xor     r9d, r9d
0x180019d6f  xor     r8d, r8d; UUID *
0x180019d72  xor     edx, edx; UUID *
0x180019d74  call    UbpmpRemoveQueuedSerialActions
0x180019d79  jmp     loc_180019B75
```
