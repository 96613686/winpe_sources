# Smb2RetrieveCreate

- ea: `0x140011214`
- end: `0x140011573`
- name: `Smb2RetrieveCreate`
- size: `863`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140079c80`

## callees

- `0x140011214`
- `0x140011580`
- `0x140012790`
- `0x140013920`
- `0x140015830`
- `0x140016df0`
- `0x140022690`
- `0x14002dca4`
- `0x140068838`
- `0x14007ca90`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140011415`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140011415`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001142d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400114ca`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001142d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400114ca`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400112d1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140011383`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400112d1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140011383`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400112f7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140011311`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400113b2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001143d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400114da`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140011529`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400112f7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140011311`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400113b2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001143d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400114da`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140011529`
- `srvnet!SrvAdminUpdateFileSessionID` at `0x1400114fd`
- `srvnet!SrvAdminUpdateFileSessionID` at `0x1400114fd`

## pseudocode

```c
__int64 __fastcall Smb2RetrieveCreate(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // rax
  __int64 v4; // rbx
  __int64 result; // rax
  __int64 WorkItemSecurityContext; // rax
  __int64 v7; // r8
  __int64 v8; // rcx
  unsigned int v9; // esi
  __int64 v10; // rax
  __int64 v11; // r13
  __int64 v12; // rax
  volatile LONG *v13; // r12
  __int64 v14; // r15
  __int64 v15; // rax
  __int64 v16; // rdx
  struct _KLOCK_QUEUE_HANDLE v17; // [rsp+30h] [rbp-38h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+48h] [rbp-20h] BYREF

  v1 = *(_QWORD *)(a1 + 560);
  v3 = RfsHashTableLookup(*(_QWORD *)(*(_QWORD *)(v1 + 152) + 144LL), v1 + 336, 16);
  v4 = v3;
  if ( !v3 )
    return 3221225494LL;
  if ( *(_BYTE *)(v3 + 237) )
  {
    if ( *(_QWORD *)(v3 + 408) )
    {
      WorkItemSecurityContext = Smb2GetWorkItemSecurityContext(v1);
      if ( (unsigned __int8)Smb2VerifySecurityContext(*(_QWORD *)(v7 + 8), WorkItemSecurityContext) )
      {
        if ( *(_QWORD *)(v1 + 104) == *(_QWORD *)(v4 + 168) )
        {
          if ( *(_DWORD *)(v4 + 88) != -1 )
          {
            memset(&LockHandle, 0, sizeof(LockHandle));
            KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v4 + 112), &LockHandle);
            v8 = *(_QWORD *)(v4 + 160);
            if ( v8 && *(_QWORD *)(v8 + 112) != *(_QWORD *)(v1 + 32) )
            {
              KeReleaseInStackQueuedSpinLock(&LockHandle);
              v9 = -1073741270;
LABEL_24:
              Smb2DereferenceFile((PVOID)v4);
              return v9;
            }
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            goto LABEL_33;
          }
          v10 = *(_QWORD *)(v1 + 56);
          memset(&v17, 0, sizeof(v17));
          v11 = *(_QWORD *)(v10 + 96);
          if ( ((_InterlockedExchangeAdd64(*(volatile signed __int64 **)(*(_QWORD *)(v1 + 32) + 24LL), 1u) + 2)
              & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
            __int2c();
          if ( ((_InterlockedExchangeAdd64(*(volatile signed __int64 **)(v1 + 56), 1u) + 2) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
            __int2c();
          v12 = *(_QWORD *)(v1 + 32);
          v13 = *(volatile LONG **)(v12 + 104);
          v14 = *(_QWORD *)(v12 + 24);
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v4 + 112), &v17);
          if ( *(_DWORD *)(v4 + 12) == 220 && *(_QWORD *)(v4 + 128) == v11 )
          {
            if ( *(_DWORD *)(v4 + 88) != -1 )
            {
              KeReleaseInStackQueuedSpinLock(&v17);
              Smb2DereferenceSession(*(_QWORD *)(v1 + 32));
              Smb2DereferenceTreeConnect(*(PVOID *)(v1 + 56));
LABEL_33:
              *(_QWORD *)(v1 + 72) = v4;
              result = 0;
              *(_BYTE *)(v1 + 307) = 1;
              return result;
            }
            if ( (unsigned __int8)RfsTableInsert(v13) )
            {
              v15 = *(_QWORD *)(v1 + 32);
              *(_QWORD *)(v4 + 152) = v14;
              *(_QWORD *)(v4 + 144) = v15;
              *(_QWORD *)(v4 + 160) = *(_QWORD *)(v1 + 56);
              KeAcquireSpinLockAtDpcLevel(&qword_14004B3E0);
              if ( *(_BYTE *)(v4 + 240) )
              {
                KeReleaseSpinLockFromDpcLevel(&qword_14004B3E0);
                KeReleaseInStackQueuedSpinLock(&v17);
                _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v1 + 32) + 112LL));
                v9 = -1073741772;
                goto LABEL_24;
              }
              if ( *(_QWORD *)(v4 + 392) != v4 + 392 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_qq(
                    WPP_GLOBAL_Control->AttachedDevice,
                    62,
                    &WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids,
                    a1,
                    v4);
                }
                LOBYTE(v16) = 1;
                Smb2RemoveFileFromDurableHandleList(v4 + 392, v16);
                ++*(_DWORD *)(Srv2Statistics + 136);
              }
              KeReleaseSpinLockFromDpcLevel(&qword_14004B3E0);
              KeReleaseInStackQueuedSpinLock(&v17);
              SrvAdminUpdateFileSessionID(
                *(_QWORD *)(v4 + 320),
                *(_QWORD *)(*(_QWORD *)(v1 + 32) + 64LL),
                **(unsigned __int8 **)(a1 + 64));
              _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v1 + 32) + 112LL));
              goto LABEL_33;
            }
            v9 = -1073741670;
          }
          else
          {
            v9 = -1073741772;
          }
          KeReleaseInStackQueuedSpinLock(&v17);
          Smb2DereferenceFile((PVOID)v4);
          Smb2DereferenceSession(*(_QWORD *)(v1 + 32));
          Smb2DereferenceTreeConnect(*(PVOID *)(v1 + 56));
          return v9;
        }
      }
    }
  }
  Smb2DereferenceFile((PVOID)v4);
  return 3221225506LL;
}

```

## disassembly

```asm
0x140011214  push    rbp
0x140011216  push    rbx
0x140011217  push    rsi
0x140011218  push    rdi
0x140011219  push    r12
0x14001121b  push    r13
0x14001121d  push    r14
0x14001121f  push    r15
0x140011221  mov     rbp, rsp
0x140011224  sub     rsp, 68h
0x140011228  mov     rdi, [rcx+230h]
0x14001122f  mov     r14, rcx
0x140011232  mov     r8d, 10h
0x140011238  mov     rcx, [rdi+98h]
0x14001123f  lea     rdx, [rdi+150h]
0x140011246  mov     rcx, [rcx+90h]
0x14001124d  call    RfsHashTableLookup
0x140011252  mov     rbx, rax
0x140011255  test    rax, rax
0x140011258  jnz     short loc_140011264
0x14001125a  mov     eax, 0C0000016h
0x14001125f  jmp     loc_140011561
0x140011264  cmp     byte ptr [rax+0EDh], 0
0x14001126b  jz      loc_140011554
0x140011271  mov     r8, [rax+198h]
0x140011278  test    r8, r8
0x14001127b  jz      loc_140011554
0x140011281  mov     rcx, rdi
0x140011284  call    Smb2GetWorkItemSecurityContext
0x140011289  mov     rcx, [r8+8]
0x14001128d  mov     rdx, rax
0x140011290  call    Smb2VerifySecurityContext
0x140011295  test    al, al
0x140011297  jz      loc_140011554
0x14001129d  mov     rax, [rbx+0A8h]
0x1400112a4  cmp     [rdi+68h], rax
0x1400112a8  jnz     loc_140011554
0x1400112ae  lea     rsi, [rbx+58h]
0x1400112b2  xor     eax, eax
0x1400112b4  cmp     dword ptr [rsi], 0FFFFFFFFh
0x1400112b7  mov     edx, 1
0x1400112bc  xorps   xmm0, xmm0
0x1400112bf  jz      short loc_140011322
0x1400112c1  lea     rcx, [rbx+70h]; SpinLock
0x1400112c5  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x1400112c9  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400112cd  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x1400112d1  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400112d8  nop     dword ptr [rax+rax+00h]
0x1400112dd  mov     rcx, [rbx+0A0h]
0x1400112e4  test    rcx, rcx
0x1400112e7  jz      short loc_14001130D
0x1400112e9  mov     rax, [rdi+20h]
0x1400112ed  cmp     [rcx+70h], rax
0x1400112f1  jz      short loc_14001130D
0x1400112f3  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400112f7  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400112fe  nop     dword ptr [rax+rax+00h]
0x140011303  mov     esi, 0C000022Ah
0x140011308  jmp     loc_140011456
0x14001130d  lea     rcx, [rbp+LockHandle]; LockHandle
0x140011311  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140011318  nop     dword ptr [rax+rax+00h]
0x14001131d  jmp     loc_140011511
0x140011322  mov     qword ptr [rbp+var_38.OldIrql], rax
0x140011326  mov     rax, [rdi+38h]
0x14001132a  movups  xmmword ptr [rbp+var_38.LockQueue.Next], xmm0
0x14001132e  mov     r13, [rax+60h]
0x140011332  mov     rax, [rdi+20h]
0x140011336  mov     rcx, [rax+18h]
0x14001133a  mov     rax, rdx
0x14001133d  lock xadd [rcx], rax
0x140011342  inc     rax
0x140011345  add     rax, rdx
0x140011348  test    rax, 0FFFFFFFFFFFFFFFEh
0x14001134e  jnz     short loc_140011352
0x140011350  int     2Ch; Windows NT - assertion failure
0x140011352  mov     rax, [rdi+38h]
0x140011356  mov     rcx, rdx
0x140011359  lock xadd [rax], rcx
0x14001135e  lea     rax, [rdx+1]
0x140011362  add     rax, rcx
0x140011365  test    rax, 0FFFFFFFFFFFFFFFEh
0x14001136b  jnz     short loc_14001136F
0x14001136d  int     2Ch; Windows NT - assertion failure
0x14001136f  mov     rax, [rdi+20h]
0x140011373  lea     rcx, [rbx+70h]; SpinLock
0x140011377  lea     rdx, [rbp+var_38]; LockHandle
0x14001137b  mov     r12, [rax+68h]
0x14001137f  mov     r15, [rax+18h]
0x140011383  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001138a  nop     dword ptr [rax+rax+00h]
0x14001138f  cmp     dword ptr [rbx+0Ch], 0DCh
0x140011396  jnz     loc_140011520
0x14001139c  cmp     [rbx+80h], r13
0x1400113a3  jnz     loc_140011520
0x1400113a9  cmp     dword ptr [rsi], 0FFFFFFFFh
0x1400113ac  jz      short loc_1400113D5
0x1400113ae  lea     rcx, [rbp+var_38]; LockHandle
0x1400113b2  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400113b9  nop     dword ptr [rax+rax+00h]
0x1400113be  mov     rcx, [rdi+20h]
0x1400113c2  call    Smb2DereferenceSession
0x1400113c7  mov     rcx, [rdi+38h]; P
0x1400113cb  call    Smb2DereferenceTreeConnect
0x1400113d0  jmp     loc_140011511
0x1400113d5  mov     rdx, rsi
0x1400113d8  mov     rcx, r12; SpinLock
0x1400113db  call    RfsTableInsert
0x1400113e0  test    al, al
0x1400113e2  jnz     short loc_1400113EE
0x1400113e4  mov     esi, 0C000009Ah
0x1400113e9  jmp     loc_140011525
0x1400113ee  mov     rax, [rdi+20h]
0x1400113f2  mov     [rbx+98h], r15
0x1400113f9  lea     r15, qword_14004B3E0
0x140011400  mov     [rbx+90h], rax
0x140011407  mov     rcx, r15; SpinLock
0x14001140a  mov     rax, [rdi+38h]
0x14001140e  mov     [rbx+0A0h], rax
0x140011415  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001141c  nop     dword ptr [rax+rax+00h]
0x140011421  cmp     byte ptr [rbx+0F0h], 0
0x140011428  jz      short loc_140011465
0x14001142a  mov     rcx, r15; SpinLock
0x14001142d  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140011434  nop     dword ptr [rax+rax+00h]
0x140011439  lea     rcx, [rbp+var_38]; LockHandle
0x14001143d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140011444  nop     dword ptr [rax+rax+00h]
0x140011449  mov     rax, [rdi+20h]
0x14001144d  lock inc dword ptr [rax+70h]
0x140011451  mov     esi, 0C0000034h
0x140011456  mov     rcx, rbx; P
0x140011459  call    Smb2DereferenceFile
0x14001145e  mov     eax, esi
0x140011460  jmp     loc_140011561
0x140011465  lea     rsi, [rbx+188h]
0x14001146c  cmp     [rsi], rsi
0x14001146f  jz      short loc_1400114C7
0x140011471  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140011478  lea     rax, WPP_GLOBAL_Control
0x14001147f  cmp     rcx, rax
0x140011482  jz      short loc_1400114B0
0x140011484  test    dword ptr [rcx+2Ch], 10000h
0x14001148b  jz      short loc_1400114B0
0x14001148d  cmp     byte ptr [rcx+29h], 2
0x140011491  jb      short loc_1400114B0
0x140011493  mov     rcx, [rcx+18h]
0x140011497  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14001149e  mov     edx, 3Eh ; '>'
0x1400114a3  mov     [rsp+68h+var_48], rbx
0x1400114a8  mov     r9, r14
0x1400114ab  call    WPP_SF_qq
0x1400114b0  mov     dl, 1
0x1400114b2  mov     rcx, rsi
0x1400114b5  call    Smb2RemoveFileFromDurableHandleList
0x1400114ba  mov     rax, cs:Srv2Statistics
0x1400114c1  inc     dword ptr [rax+88h]
0x1400114c7  mov     rcx, r15; SpinLock
0x1400114ca  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400114d1  nop     dword ptr [rax+rax+00h]
0x1400114d6  lea     rcx, [rbp+var_38]; LockHandle
0x1400114da  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400114e1  nop     dword ptr [rax+rax+00h]
0x1400114e6  mov     rax, [r14+40h]
0x1400114ea  mov     rdx, [rdi+20h]
0x1400114ee  mov     rcx, [rbx+140h]
0x1400114f5  movzx   r8d, byte ptr [rax]
0x1400114f9  mov     rdx, [rdx+40h]
0x1400114fd  call    cs:__imp_SrvAdminUpdateFileSessionID
0x140011504  nop     dword ptr [rax+rax+00h]
0x140011509  mov     rax, [rdi+20h]
0x14001150d  lock inc dword ptr [rax+70h]
0x140011511  mov     [rdi+48h], rbx
0x140011515  xor     eax, eax
0x140011517  mov     byte ptr [rdi+133h], 1
0x14001151e  jmp     short loc_140011561
0x140011520  mov     esi, 0C0000034h
0x140011525  lea     rcx, [rbp+var_38]; LockHandle
0x140011529  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140011530  nop     dword ptr [rax+rax+00h]
0x140011535  mov     rcx, rbx; P
0x140011538  call    Smb2DereferenceFile
0x14001153d  mov     rcx, [rdi+20h]
0x140011541  call    Smb2DereferenceSession
0x140011546  mov     rcx, [rdi+38h]; P
0x14001154a  call    Smb2DereferenceTreeConnect
0x14001154f  jmp     loc_14001145E
0x140011554  mov     rcx, rbx; P
0x140011557  call    Smb2DereferenceFile
0x14001155c  mov     eax, 0C0000022h
0x140011561  add     rsp, 68h
0x140011565  pop     r15
0x140011567  pop     r14
0x140011569  pop     r13
0x14001156b  pop     r12
0x14001156d  pop     rdi
0x14001156e  pop     rsi
0x14001156f  pop     rbx
0x140011570  pop     rbp
0x140011571  retn
```
