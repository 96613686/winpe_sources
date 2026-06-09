# LRPC_SASSOCIATION::AllocateCall(LRPC_SCALL * *,ulong)

- ea: `0x18001aca4`
- end: `0x18001ae55`
- name: `?AllocateCall@LRPC_SASSOCIATION@@AEAAJPEAPEAVLRPC_SCALL@@K@Z`
- size: `433`
- prototype: `__int64 __fastcall(LRPC_SASSOCIATION *__hidden this, struct LRPC_SCALL **, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a690`

## callees

- `0x18001831c`
- `0x180019640`
- `0x180019b58`
- `0x18001aca4`
- `0x18001c008`
- `0x180023020`
- `0x1800d7010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18001add9`
- `ntdll!EtwEventActivityIdControl` at `0x18001add9`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18001ace3`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18001ace3`

## pseudocode

```c
__int64 __fastcall LRPC_SASSOCIATION::AllocateCall(union _SLIST_HEADER *this, struct LRPC_SCALL **a2, unsigned int a3)
{
  signed __int64 Alignment; // rbx
  PSLIST_ENTRY v7; // rax
  bool v8; // zf
  unsigned int v10; // edi
  LRPC_SCALL *v11; // rax
  LRPC_SCALL *v12; // rax
  struct LRPC_SCALL *v13; // rbx
  LRPC_SCALL *v14; // rax
  int v15; // [rsp+40h] [rbp+8h] BYREF

  Alignment = this[25].Alignment;
  if ( !Alignment || Alignment != _InterlockedCompareExchange64((volatile signed __int64 *)&this[25], 0, Alignment) )
  {
    v7 = InterlockedPopEntrySList(this + 26);
    if ( !v7 || (Alignment = (signed __int64)&v7[-37], v7 == (PSLIST_ENTRY)592) )
    {
      v10 = 0;
      v15 = 0;
      if ( gfRPCVerifierEnabled )
      {
        v14 = (LRPC_SCALL *)AllocWrapper(0x290u);
        v13 = v14;
        if ( v14 )
        {
          LRPC_SCALL::LRPC_SCALL(v14, &v15, (struct LRPC_SASSOCIATION *)this, a3);
          v10 = v15;
          *(_QWORD *)v13 = &LRPC_SCALL_AVRF::`vftable';
LABEL_12:
          if ( v10 )
          {
            (*(void (__fastcall **)(struct LRPC_SCALL *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 1);
          }
          else
          {
            *a2 = v13;
            CALL::CreateAndSetActivityId(v13);
          }
          return v10;
        }
        v13 = 0;
      }
      else
      {
        v11 = (LRPC_SCALL *)AllocWrapper(0x290u);
        if ( !v11 )
          return 14;
        v12 = LRPC_SCALL::LRPC_SCALL(v11, &v15, (struct LRPC_SASSOCIATION *)this, a3);
        v10 = v15;
        v13 = v12;
      }
      if ( v13 )
        goto LABEL_12;
      return 14;
    }
  }
  *(_QWORD *)(Alignment + 24) = 0;
  *(_QWORD *)(Alignment + 40) = 0;
  *(_QWORD *)(Alignment + 312) = 0;
  *(_DWORD *)(Alignment + 532) = a3;
  *(_QWORD *)(Alignment + 592) = 0;
  REFERENCED_OBJECT::SingleThreadedAddReference((REFERENCED_OBJECT *)Alignment);
  v8 = dword_1800FE624 == 0;
  *a2 = (struct LRPC_SCALL *)Alignment;
  if ( v8 )
  {
    *(GUID *)(Alignment + 208) = g_NullActivityId;
  }
  else
  {
    if ( UuidCreate((UUID *)(Alignment + 208)) )
      *(GUID *)(Alignment + 208) = g_NullActivityId;
    EtwEventActivityIdControl(2);
  }
  return 0;
}

```

## disassembly

```asm
0x18001aca4  mov     [rsp+arg_8], rbx
0x18001aca9  mov     [rsp+arg_10], rbp
0x18001acae  push    rsi
0x18001acaf  push    rdi
0x18001acb0  push    r14
0x18001acb2  sub     rsp, 20h
0x18001acb6  mov     rbx, [rcx+190h]
0x18001acbd  mov     ebp, r8d
0x18001acc0  mov     r14, rdx
0x18001acc3  mov     rsi, rcx
0x18001acc6  test    rbx, rbx
0x18001acc9  jz      short loc_18001ACDC
0x18001accb  xor     r9d, r9d
0x18001acce  mov     rax, rbx
0x18001acd1  lock cmpxchg [rcx+190h], r9
0x18001acda  jz      short loc_18001AD00
0x18001acdc  add     rcx, 1A0h; ListHead
0x18001ace3  call    cs:__imp_InterlockedPopEntrySList
0x18001acea  nop     dword ptr [rax+rax+00h]
0x18001acef  test    rax, rax
0x18001acf2  jz      short loc_18001AD66
0x18001acf4  lea     rbx, [rax-250h]
0x18001acfb  test    rbx, rbx
0x18001acfe  jz      short loc_18001AD66
0x18001ad00  mov     qword ptr [rbx+18h], 0
0x18001ad08  mov     rcx, rbx; this
0x18001ad0b  mov     qword ptr [rbx+28h], 0
0x18001ad13  mov     qword ptr [rbx+138h], 0
0x18001ad1e  mov     [rbx+214h], ebp
0x18001ad24  mov     qword ptr [rbx+250h], 0
0x18001ad2f  nop
0x18001ad30  call    ?SingleThreadedAddReference@REFERENCED_OBJECT@@QEAAXXZ; REFERENCED_OBJECT::SingleThreadedAddReference(void)
0x18001ad35  cmp     cs:dword_1800FE624, 0
0x18001ad3c  mov     [r14], rbx
0x18001ad3f  jnz     short loc_18001ADBD
0x18001ad41  movups  xmm0, xmmword ptr cs:?g_NullActivityId@@3U_GUID@@B.Data1; _GUID const g_NullActivityId ...
0x18001ad48  movdqu  xmmword ptr [rbx+0D0h], xmm0
0x18001ad50  xor     eax, eax
0x18001ad52  mov     rbx, [rsp+38h+arg_8]
0x18001ad57  mov     rbp, [rsp+38h+arg_10]
0x18001ad5c  add     rsp, 20h
0x18001ad60  pop     r14
0x18001ad62  pop     rdi
0x18001ad63  pop     rsi
0x18001ad64  retn
0x18001ad66  xor     edi, edi
0x18001ad68  mov     ecx, 290h; dwBytes
0x18001ad6d  cmp     cs:?gfRPCVerifierEnabled@@3HA, edi; int gfRPCVerifierEnabled
0x18001ad73  mov     [rsp+38h+arg_0], edi
0x18001ad77  jnz     loc_18001AE02
0x18001ad7d  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18001ad82  test    rax, rax
0x18001ad85  jz      short loc_18001ADEA
0x18001ad87  mov     r9d, ebp; unsigned int
0x18001ad8a  lea     rdx, [rsp+38h+arg_0]; int *
0x18001ad8f  mov     r8, rsi; struct LRPC_SASSOCIATION *
0x18001ad92  mov     rcx, rax; this
0x18001ad95  call    ??0LRPC_SCALL@@QEAA@PEAJPEAVLRPC_SASSOCIATION@@K@Z; LRPC_SCALL::LRPC_SCALL(long *,LRPC_SASSOCIATION *,ulong)
0x18001ad9a  mov     edi, [rsp+38h+arg_0]
0x18001ad9e  mov     rbx, rax
0x18001ada1  test    rbx, rbx
0x18001ada4  jz      short loc_18001ADEA
0x18001ada6  test    edi, edi
0x18001ada8  jnz     loc_18001AE35
0x18001adae  mov     rcx, rbx; this
0x18001adb1  mov     [r14], rbx
0x18001adb4  call    ?CreateAndSetActivityId@CALL@@QEAAXXZ; CALL::CreateAndSetActivityId(void)
0x18001adb9  mov     eax, edi
0x18001adbb  jmp     short loc_18001AD52
0x18001adbd  lea     rcx, [rbx+0D0h]; Uuid
0x18001adc4  call    UuidCreate
0x18001adc9  test    eax, eax
0x18001adcb  jnz     short loc_18001ADF1
0x18001adcd  lea     rdx, [rbx+0D0h]
0x18001add4  mov     ecx, 2
0x18001add9  call    cs:__imp_EtwEventActivityIdControl
0x18001ade0  nop     dword ptr [rax+rax+00h]
0x18001ade5  jmp     loc_18001AD50
0x18001adea  mov     edi, 0Eh
0x18001adef  jmp     short loc_18001ADB9
0x18001adf1  movups  xmm0, xmmword ptr cs:?g_NullActivityId@@3U_GUID@@B.Data1; _GUID const g_NullActivityId ...
0x18001adf8  movdqu  xmmword ptr [rbx+0D0h], xmm0
0x18001ae00  jmp     short loc_18001ADCD
0x18001ae02  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18001ae07  mov     rbx, rax
0x18001ae0a  test    rax, rax
0x18001ae0d  jz      short loc_18001AE4E
0x18001ae0f  mov     r9d, ebp; unsigned int
0x18001ae12  lea     rdx, [rsp+38h+arg_0]; int *
0x18001ae17  mov     r8, rsi; struct LRPC_SASSOCIATION *
0x18001ae1a  mov     rcx, rax; this
0x18001ae1d  call    ??0LRPC_SCALL@@QEAA@PEAJPEAVLRPC_SASSOCIATION@@K@Z; LRPC_SCALL::LRPC_SCALL(long *,LRPC_SASSOCIATION *,ulong)
0x18001ae22  mov     edi, [rsp+38h+arg_0]
0x18001ae26  lea     rax, ??_7LRPC_SCALL_AVRF@@6B@; const LRPC_SCALL_AVRF::`vftable'
0x18001ae2d  mov     [rbx], rax
0x18001ae30  jmp     loc_18001ADA6
0x18001ae35  mov     rcx, [rbx]
0x18001ae38  mov     edx, 1
0x18001ae3d  mov     rax, [rcx+8]
0x18001ae41  mov     rcx, rbx
0x18001ae44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae49  jmp     loc_18001ADB9
0x18001ae4e  xor     ebx, ebx
0x18001ae50  jmp     loc_18001ADA1
```
