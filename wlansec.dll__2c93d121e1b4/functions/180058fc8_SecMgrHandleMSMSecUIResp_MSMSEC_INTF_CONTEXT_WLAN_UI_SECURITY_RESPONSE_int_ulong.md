# SecMgrHandleMSMSecUIResp(MSMSEC_INTF_CONTEXT *,_WLAN_UI_SECURITY_RESPONSE *,int,ulong)

- ea: `0x180058fc8`
- end: `0x1800595fd`
- name: `?SecMgrHandleMSMSecUIResp@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAU_WLAN_UI_SECURITY_RESPONSE@@HK@Z`
- size: `1589`
- prototype: `unsigned int __fastcall(struct MSMSEC_INTF_CONTEXT *, struct _WLAN_UI_SECURITY_RESPONSE *, int, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032910`

## callees

- `0x180006344`
- `0x18000892c`
- `0x180008998`
- `0x18000a26c`
- `0x18000b6dc`
- `0x180011030`
- `0x180014998`
- `0x1800169c0`
- `0x180016a08`
- `0x18001d8ac`
- `0x18001f29c`
- `0x180021fd0`
- `0x18002589c`
- `0x18002ddd4`
- `0x1800558c0`
- `0x18005639c`
- `0x180058fc8`
- `0x18005a25c`
- `0x18005a440`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800595b0`
- `MobileNetworking!ReleaseWriteLock` at `0x1800595b0`

## pseudocode

```c
__int64 __fastcall SecMgrHandleMSMSecUIResp(
        struct MSMSEC_INTF_CONTEXT *a1,
        struct _WLAN_UI_SECURITY_RESPONSE *a2,
        int a3,
        unsigned int a4)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  int v11; // edx
  const wchar_t *v12; // rax
  unsigned int v13; // r10d
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // r11
  __int64 v17; // r8
  char v18; // r10
  _QWORD *v19; // rsi
  __int64 v20; // rcx
  int v21; // r9d
  _QWORD *v22; // rbx
  _QWORD *v23; // rcx
  __int64 v24; // r9
  __int64 v25; // rdx
  unsigned int v26; // eax
  _DWORD *v27; // rax
  unsigned int v28; // ebx
  const char *v29; // r9
  _DWORD v31[2]; // [rsp+40h] [rbp-38h] BYREF
  char *v32; // [rsp+48h] [rbp-30h]
  __int128 v33; // [rsp+50h] [rbp-28h] BYREF
  __int64 v34; // [rsp+60h] [rbp-18h]

  v31[1] = 0;
  v33 = 0;
  v34 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 141, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
  v8 = SecMgrLockAndCheckAdapterDeleted(a1, (__int64)a2, a3);
  v9 = v8;
  if ( !v8 )
  {
    if ( !(unsigned int)IsValidIntfSecStateForAction(*((unsigned int *)a1 + 681), 8) )
    {
      v9 = 5023;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v12 = IntfActionStr(8);
        v15 = IntfSecStateStr(v13, v14, v12);
        WPP_SF_SLSL(
          *(_QWORD *)(v16 + 56),
          143,
          (unsigned int)&WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids,
          v15,
          v18,
          v17,
          8);
      }
      goto LABEL_83;
    }
    if ( a3 )
    {
      if ( a4 == 11 )
      {
        v28 = 294930;
LABEL_70:
        if ( (byte_1800AED45 & 2) != 0 )
          McTemplateU0qjqqtt_EventWriteTransfer(
            *(_QWORD *)(*((_QWORD *)a1 + 348) + 24LL),
            v11,
            *((_DWORD *)a1 + 624),
            (_DWORD)a1 + 32,
            **(_DWORD **)(*((_QWORD *)a1 + 348) + 24LL),
            *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 348) + 24LL) + 4LL),
            *(_DWORD *)(*((_QWORD *)a1 + 348) + 32LL),
            a3);
        SecMgrIntfStateTransition(a1, 8, v28);
        v26 = MSMConnectCompletion(
                *((_DWORD *)a1 + 624),
                *((void **)a1 + 3),
                *((void **)a1 + 328),
                v28,
                a4,
                *((unsigned int (**)(void *, void *, unsigned int, unsigned int))a1 + 269));
        v9 = v26;
        if ( !v26 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
          {
            v29 = "user cancellation";
            if ( !a3 )
              v29 = "incorrect response type";
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 7), 145, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v29);
          }
          goto LABEL_83;
        }
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        {
LABEL_83:
          TraceAdapterId(*((_DWORD *)a1 + 624), "<<< Unlocking <<<");
          ReleaseWriteLock(a1, (char *)a1 + 2512, "SecMgrHandleMSMSecUIResp", 2395);
          goto LABEL_84;
        }
        v25 = 144;
        goto LABEL_76;
      }
    }
    else
    {
      v19 = (_QWORD *)((char *)a1 + 2784);
      if ( (unsigned int)ValidUIRespForConfig(
                           *(unsigned int *)a2,
                           **(unsigned int **)(*((_QWORD *)a1 + 348) + 24LL),
                           *(unsigned int *)(*(_QWORD *)(*((_QWORD *)a1 + 348) + 24LL) + 4LL),
                           *(unsigned int *)(*((_QWORD *)a1 + 348) + 32LL)) )
      {
        if ( (unsigned int)RawDataIsNonEmpty(*v19 + 64LL) )
        {
          if ( (byte_1800AED45 & 2) != 0 )
            McTemplateU0qj_EventWriteTransfer(
              v20,
              (const char *)MsmSecSecMgrAlreadyHaveKey,
              *((unsigned int *)a1 + 624));
          v9 = 5023;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 146, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
          goto LABEL_83;
        }
        v32 = (char *)a2 + 16;
        v31[0] = *((_DWORD *)a2 + 1);
        if ( (byte_1800AED45 & 1) != 0 )
          McTemplateU0qjq_EventWriteTransfer(
            v20,
            (unsigned int)MsmSecSecMgrReceivedUIResponse,
            *((_DWORD *)a1 + 624),
            v21,
            *(_DWORD *)a2);
        v22 = (_QWORD *)((char *)a1 + 2784);
        if ( *(_DWORD *)a2 )
        {
          if ( *(_DWORD *)a2 != 1 )
          {
            if ( *(_DWORD *)a2 != 2 )
            {
              v9 = 13;
              v23 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
                goto LABEL_83;
              v24 = *(unsigned int *)a2;
              v25 = 156;
              goto LABEL_77;
            }
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            {
              v22 = (_QWORD *)((char *)a1 + 2784);
            }
            else if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 153, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
            }
            v26 = CopyKey(0, v31, *v22 + 64LL);
            v9 = v26;
            if ( v26 )
            {
              v23 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
                goto LABEL_83;
              v25 = 154;
              goto LABEL_76;
            }
            v26 = CopyKey(0, v31, *((_QWORD *)a1 + 349) + 64LL);
            v9 = v26;
            if ( v26 )
            {
              v23 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
                goto LABEL_83;
              v25 = 155;
              goto LABEL_76;
            }
            goto LABEL_52;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 150, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
          v26 = CopyKey(0, v31, *v19 + 64LL);
          v9 = v26;
          if ( v26 )
          {
            v23 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
              goto LABEL_83;
            v25 = 151;
            goto LABEL_76;
          }
          *(_DWORD *)*v19 |= 2u;
          v26 = CopyKey(0, v31, *((_QWORD *)a1 + 349) + 64LL);
          v9 = v26;
          if ( v26 )
          {
            v23 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
              goto LABEL_83;
            v25 = 152;
            goto LABEL_76;
          }
          **((_DWORD **)a1 + 349) |= 2u;
LABEL_52:
          v27 = (_DWORD *)*v19;
          LODWORD(v33) = 2;
          *((_QWORD *)&v33 + 1) = a1;
          *v27 |= 1u;
          **((_DWORD **)a1 + 349) |= 1u;
          v34 = *((_QWORD *)a1 + 328);
          SecMgrIntfStateTransition(a1, 2, 327679);
          *((_DWORD *)a1 + 700) = 1;
          v26 = SecMgrPreAssociateCompletionLocked((struct API_CONTEXT_BASE *)&v33);
          v9 = v26;
          if ( !v26 )
            goto LABEL_83;
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_83;
          v25 = 157;
          goto LABEL_76;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 147, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
        v26 = CopyKey(0, v31, *v19 + 64LL);
        v9 = v26;
        if ( v26 )
        {
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_83;
          v25 = 148;
        }
        else
        {
          v26 = CopyKey(0, v31, *((_QWORD *)a1 + 349) + 64LL);
          v9 = v26;
          if ( !v26 )
            goto LABEL_52;
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_83;
          v25 = 149;
        }
LABEL_76:
        v24 = v26;
LABEL_77:
        WPP_SF_d(v23[7], v25, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v24);
        goto LABEL_83;
      }
    }
    v28 = 294929;
    goto LABEL_70;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 142, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v8);
LABEL_84:
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x100) != 0 )
    WPP_SF_d(v10[7], 158, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180058fc8  push    rbp
0x180058fca  push    rbx
0x180058fcb  push    rsi
0x180058fcc  push    rdi
0x180058fcd  push    r12
0x180058fcf  push    r13
0x180058fd1  push    r14
0x180058fd3  push    r15
0x180058fd5  mov     rbp, rsp
0x180058fd8  sub     rsp, 78h
0x180058fdc  xorps   xmm0, xmm0
0x180058fdf  mov     [rbp+var_34], 0
0x180058fe6  xor     eax, eax
0x180058fe8  mov     r12d, r9d
0x180058feb  movups  [rbp+var_28], xmm0
0x180058fef  mov     [rbp+var_18], rax
0x180058ff3  mov     r15d, r8d
0x180058ff6  mov     r14, rdx
0x180058ff9  mov     rdi, rcx
0x180058ffc  mov     rcx, cs:WPP_GLOBAL_Control
0x180059003  lea     r13, WPP_GLOBAL_Control
0x18005900a  cmp     rcx, r13
0x18005900d  jz      short loc_18005902D
0x18005900f  test    dword ptr [rcx+44h], 100h
0x180059016  jz      short loc_18005902D
0x180059018  mov     rcx, [rcx+38h]
0x18005901c  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180059023  mov     edx, 8Dh
0x180059028  call    WPP_SF_
0x18005902d  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180059030  call    ?SecMgrLockAndCheckAdapterDeleted@@YAKPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrLockAndCheckAdapterDeleted(MSMSEC_INTF_CONTEXT *)
0x180059035  mov     ebx, eax
0x180059037  test    eax, eax
0x180059039  jz      short loc_180059072
0x18005903b  mov     rcx, cs:WPP_GLOBAL_Control
0x180059042  cmp     rcx, r13
0x180059045  jz      loc_1800595E9
0x18005904b  test    byte ptr [rcx+44h], 1
0x18005904f  jz      loc_1800595C3
0x180059055  mov     rcx, [rcx+38h]
0x180059059  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180059060  mov     edx, 8Eh
0x180059065  mov     r9d, eax
0x180059068  call    WPP_SF_d
0x18005906d  jmp     loc_1800595BC
0x180059072  mov     ecx, [rdi+0AA4h]
0x180059078  mov     esi, 8
0x18005907d  mov     edx, esi
0x18005907f  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x180059084  test    eax, eax
0x180059086  jnz     short loc_1800590EC
0x180059088  mov     ebx, 139Fh
0x18005908d  mov     r11, cs:WPP_GLOBAL_Control
0x180059094  cmp     r11, r13
0x180059097  jz      loc_180059587
0x18005909d  test    byte ptr [r11+44h], 1
0x1800590a2  jz      loc_180059587
0x1800590a8  mov     r10d, [rdi+0AA4h]
0x1800590af  mov     ecx, esi
0x1800590b1  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x1800590b6  mov     ecx, r10d
0x1800590b9  mov     r8, rax
0x1800590bc  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x1800590c1  mov     rcx, [r11+38h]
0x1800590c5  mov     r9, rax
0x1800590c8  mov     [rsp+78h+var_48], esi
0x1800590cc  mov     edx, 8Fh
0x1800590d1  mov     [rsp+78h+var_50], r8
0x1800590d6  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x1800590dd  mov     [rsp+78h+var_58], r10d
0x1800590e2  call    WPP_SF_SLSL
0x1800590e7  jmp     loc_180059587
0x1800590ec  test    r15d, r15d
0x1800590ef  jnz     loc_18005948B
0x1800590f5  mov     ecx, [r14]
0x1800590f8  lea     rsi, [rdi+0AE0h]
0x1800590ff  mov     r9, [rsi]
0x180059102  mov     rdx, [r9+18h]
0x180059106  mov     r9d, [r9+20h]
0x18005910a  mov     r8d, [rdx+4]
0x18005910e  mov     edx, [rdx]
0x180059110  call    ?ValidUIRespForConfig@@YAHW4_MSMSEC_UI_RESPONSE_TYPE@@W4_DOT11_AUTH_ALGORITHM@@W4_DOT11_CIPHER_ALGORITHM@@H@Z; ValidUIRespForConfig(_MSMSEC_UI_RESPONSE_TYPE,_DOT11_AUTH_ALGORITHM,_DOT11_CIPHER_ALGORITHM,int)
0x180059115  test    eax, eax
0x180059117  jz      loc_180059498
0x18005911d  mov     rcx, [rsi]
0x180059120  lea     r9, [rdi+20h]
0x180059124  add     rcx, 40h ; '@'
0x180059128  call    RawDataIsNonEmpty
0x18005912d  test    eax, eax
0x18005912f  jz      short loc_180059186
0x180059131  test    cs:byte_1800AED45, 2
0x180059138  jz      short loc_18005914D
0x18005913a  mov     r8d, [rdi+9C0h]
0x180059141  lea     rdx, MsmSecSecMgrAlreadyHaveKey
0x180059148  call    McTemplateU0qj_EventWriteTransfer
0x18005914d  mov     ebx, 139Fh
0x180059152  mov     rcx, cs:WPP_GLOBAL_Control
0x180059159  cmp     rcx, r13
0x18005915c  jz      loc_180059587
0x180059162  test    byte ptr [rcx+44h], 1
0x180059166  jz      loc_180059587
0x18005916c  mov     rcx, [rcx+38h]
0x180059170  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180059177  mov     edx, 92h
0x18005917c  call    WPP_SF_
0x180059181  jmp     loc_180059587
0x180059186  test    cs:byte_1800AED45, 1
0x18005918d  lea     rax, [r14+10h]
0x180059191  mov     [rbp+var_30], rax
0x180059195  mov     eax, [r14+4]
0x180059199  mov     [rbp+var_38], eax
0x18005919c  jz      short loc_1800591C1
0x18005919e  mov     eax, [r14]
0x1800591a1  lea     rdx, MsmSecSecMgrReceivedUIResponse
0x1800591a8  mov     r8d, [rdi+9C0h]
0x1800591af  mov     [rsp+78h+var_58], eax
0x1800591b3  call    McTemplateU0qjq_EventWriteTransfer
0x1800591b8  lea     rbx, [rdi+0AE0h]
0x1800591bf  jmp     short loc_1800591C4
0x1800591c1  mov     rbx, rsi
0x1800591c4  mov     ecx, [r14]
0x1800591c7  test    ecx, ecx
0x1800591c9  jz      loc_1800593E4
0x1800591cf  sub     ecx, 1
0x1800591d2  jz      loc_1800592B5
0x1800591d8  cmp     ecx, 1
0x1800591db  jz      short loc_180059209
0x1800591dd  mov     ebx, 0Dh
0x1800591e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800591e9  cmp     rcx, r13
0x1800591ec  jz      loc_180059587
0x1800591f2  test    byte ptr [rcx+44h], 1
0x1800591f6  jz      loc_180059587
0x1800591fc  mov     r9d, [r14]
0x1800591ff  mov     edx, 9Ch
0x180059204  jmp     loc_180059539
0x180059209  mov     rcx, cs:WPP_GLOBAL_Control
0x180059210  cmp     rcx, r13
0x180059213  jz      short loc_180059232
0x180059215  test    byte ptr [rcx+44h], 2
0x180059219  jz      short loc_180059235
0x18005921b  mov     rcx, [rcx+38h]
0x18005921f  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180059226  mov     edx, 99h
0x18005922b  call    WPP_SF_
0x180059230  jmp     short loc_180059235
0x180059232  mov     rbx, rsi
0x180059235  mov     r8, [rbx]
0x180059238  lea     rdx, [rbp+var_38]
0x18005923c  add     r8, 40h ; '@'
0x180059240  xor     ecx, ecx
0x180059242  call    CopyKey
0x180059247  mov     ebx, eax
0x180059249  test    eax, eax
0x18005924b  jz      short loc_180059271
0x18005924d  mov     rcx, cs:WPP_GLOBAL_Control
0x180059254  cmp     rcx, r13
0x180059257  jz      loc_180059587
0x18005925d  test    byte ptr [rcx+44h], 1
0x180059261  jz      loc_180059587
0x180059267  mov     edx, 9Ah
0x18005926c  jmp     loc_180059536
0x180059271  mov     r8, [rdi+0AE8h]
0x180059278  lea     rdx, [rbp+var_38]
0x18005927c  add     r8, 40h ; '@'
0x180059280  xor     ecx, ecx
0x180059282  call    CopyKey
0x180059287  mov     ebx, eax
0x180059289  test    eax, eax
0x18005928b  jz      loc_180059368
0x180059291  mov     rcx, cs:WPP_GLOBAL_Control
0x180059298  cmp     rcx, r13
0x18005929b  jz      loc_180059587
0x1800592a1  test    byte ptr [rcx+44h], 1
0x1800592a5  jz      loc_180059587
0x1800592ab  mov     edx, 9Bh
0x1800592b0  jmp     loc_180059536
0x1800592b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800592bc  cmp     rcx, r13
0x1800592bf  jz      short loc_1800592DC
0x1800592c1  test    byte ptr [rcx+44h], 2
0x1800592c5  jz      short loc_1800592DC
0x1800592c7  mov     rcx, [rcx+38h]
0x1800592cb  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x1800592d2  mov     edx, 96h
0x1800592d7  call    WPP_SF_
0x1800592dc  mov     r8, [rsi]
0x1800592df  lea     rdx, [rbp+var_38]
0x1800592e3  add     r8, 40h ; '@'
0x1800592e7  xor     ecx, ecx
0x1800592e9  call    CopyKey
0x1800592ee  mov     ebx, eax
0x1800592f0  test    eax, eax
0x1800592f2  jz      short loc_180059318
0x1800592f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800592fb  cmp     rcx, r13
0x1800592fe  jz      loc_180059587
0x180059304  test    byte ptr [rcx+44h], 1
0x180059308  jz      loc_180059587
0x18005930e  mov     edx, 97h
0x180059313  jmp     loc_180059536
0x180059318  mov     rax, [rsi]
0x18005931b  lea     rdx, [rbp+var_38]
0x18005931f  xor     ecx, ecx
0x180059321  or      dword ptr [rax], 2
0x180059324  mov     r8, [rdi+0AE8h]
0x18005932b  add     r8, 40h ; '@'
0x18005932f  call    CopyKey
0x180059334  mov     ebx, eax
0x180059336  test    eax, eax
0x180059338  jz      short loc_18005935E
0x18005933a  mov     rcx, cs:WPP_GLOBAL_Control
0x180059341  cmp     rcx, r13
0x180059344  jz      loc_180059587
0x18005934a  test    byte ptr [rcx+44h], 1
0x18005934e  jz      loc_180059587
0x180059354  mov     edx, 98h
0x180059359  jmp     loc_180059536
0x18005935e  mov     rax, [rdi+0AE8h]
0x180059365  or      dword ptr [rax], 2
0x180059368  mov     rax, [rsi]
0x18005936b  xor     r9d, r9d
0x18005936e  mov     r8d, 4FFFFh
0x180059374  mov     dword ptr [rbp+var_28], 2
0x18005937b  mov     rcx, rdi
0x18005937e  mov     qword ptr [rbp+var_28+8], rdi
0x180059382  or      dword ptr [rax], 1
0x180059385  lea     edx, [r9+2]
0x180059389  mov     rax, [rdi+0AE8h]
0x180059390  or      dword ptr [rax], 1
0x180059393  mov     rax, [rdi+0A40h]
0x18005939a  mov     [rbp+var_18], rax
0x18005939e  call    ?SecMgrIntfStateTransition@@YAXPEAUMSMSEC_INTF_CONTEXT@@W4MSMSEC_INTF_SEC_STATE@@KK@Z; SecMgrIntfStateTransition(MSMSEC_INTF_CONTEXT *,MSMSEC_INTF_SEC_STATE,ulong,ulong)
0x1800593a3  lea     rcx, [rbp+var_28]; struct API_CONTEXT_BASE *
0x1800593a7  mov     dword ptr [rdi+0AF0h], 1
0x1800593b1  call    ?SecMgrPreAssociateCompletionLocked@@YAKPEAUAPI_CONTEXT_BASE@@@Z; SecMgrPreAssociateCompletionLocked(API_CONTEXT_BASE *)
0x1800593b6  mov     ebx, eax
0x1800593b8  test    eax, eax
0x1800593ba  jz      loc_180059587
0x1800593c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800593c7  cmp     rcx, r13
0x1800593ca  jz      loc_180059587
0x1800593d0  test    byte ptr [rcx+44h], 1
0x1800593d4  jz      loc_180059587
0x1800593da  mov     edx, 9Dh
0x1800593df  jmp     loc_180059536
0x1800593e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800593eb  cmp     rcx, r13
0x1800593ee  jz      short loc_18005940B
0x1800593f0  test    byte ptr [rcx+44h], 2
0x1800593f4  jz      short loc_18005940B
0x1800593f6  mov     rcx, [rcx+38h]
0x1800593fa  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180059401  mov     edx, 93h
0x180059406  call    WPP_SF_
0x18005940b  mov     r8, [rsi]
0x18005940e  lea     rdx, [rbp+var_38]
0x180059412  add     r8, 40h ; '@'
0x180059416  xor     ecx, ecx
0x180059418  call    CopyKey
0x18005941d  mov     ebx, eax
0x18005941f  test    eax, eax
0x180059421  jz      short loc_180059447
0x180059423  mov     rcx, cs:WPP_GLOBAL_Control
0x18005942a  cmp     rcx, r13
0x18005942d  jz      loc_180059587
0x180059433  test    byte ptr [rcx+44h], 1
0x180059437  jz      loc_180059587
0x18005943d  mov     edx, 94h
0x180059442  jmp     loc_180059536
0x180059447  mov     r8, [rdi+0AE8h]
0x18005944e  lea     rdx, [rbp+var_38]
0x180059452  add     r8, 40h ; '@'
0x180059456  xor     ecx, ecx
0x180059458  call    CopyKey
0x18005945d  mov     ebx, eax
0x18005945f  test    eax, eax
0x180059461  jz      loc_180059368
0x180059467  mov     rcx, cs:WPP_GLOBAL_Control
0x18005946e  cmp     rcx, r13
0x180059471  jz      loc_180059587
0x180059477  test    byte ptr [rcx+44h], 1
0x18005947b  jz      loc_180059587
0x180059481  mov     edx, 95h
0x180059486  jmp     loc_180059536
0x18005948b  cmp     r12d, 0Bh
0x18005948f  jnz     short loc_18005949D
0x180059491  mov     ebx, 48012h
0x180059496  jmp     short loc_1800594A2
0x180059498  mov     esi, 8
0x18005949d  mov     ebx, 48011h
0x1800594a2  test    cs:byte_1800AED45, 2
0x1800594a9  jz      short loc_1800594DF
0x1800594ab  mov     rax, [rdi+0AE0h]
0x1800594b2  lea     r9, [rdi+20h]
0x1800594b6  mov     r8d, [rdi+9C0h]
0x1800594bd  mov     [rsp+78h+var_40], r15d
0x1800594c2  mov     rcx, [rax+18h]
0x1800594c6  mov     eax, [rax+20h]
0x1800594c9  mov     [rsp+78h+var_48], eax
  ... truncated ...
```
