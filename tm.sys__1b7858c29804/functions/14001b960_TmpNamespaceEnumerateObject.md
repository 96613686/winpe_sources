# TmpNamespaceEnumerateObject

- ea: `0x14001b960`
- end: `0x14001babd`
- name: `TmpNamespaceEnumerateObject`
- size: `349`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002080`
- `0x14001b888`

## callees

- `0x14001b960`
- `0x14001be40`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001b9b3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001b9b3`
- `ntoskrnl!KeReleaseMutex` at `0x14001ba98`
- `ntoskrnl!KeReleaseMutex` at `0x14002153e`
- `ntoskrnl!KeReleaseMutex` at `0x14001ba98`
- `ntoskrnl!KeReleaseMutex` at `0x14002153e`
- `ntoskrnl!ObfDereferenceObject` at `0x14001ba77`
- `ntoskrnl!ObfDereferenceObject` at `0x14001ba77`
- `ntoskrnl!ObfReferenceObject` at `0x14001ba39`
- `ntoskrnl!ObfReferenceObject` at `0x14001ba39`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x14001ba05`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x14001ba05`

## pseudocode

```c
__int64 __fastcall TmpNamespaceEnumerateObject(__int64 a1, void *a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  _BYTE *v6; // rdi
  _BYTE *v7; // rax
  _BYTE *v8; // rsi
  unsigned int v9; // ebx
  __int128 v11; // [rsp+50h] [rbp-28h] BYREF
  PVOID RestartKey; // [rsp+90h] [rbp+18h] BYREF
  ULONG DeleteCount; // [rsp+98h] [rbp+20h] BYREF
  int v14; // [rsp+9Ch] [rbp+24h]

  v14 = HIDWORD(a4);
  RestartKey = 0;
  DeleteCount = 0;
  v6 = 0;
  v11 = 0;
  KeWaitForSingleObject(&Mutex, Executive, 0, 0, 0);
  DWORD2(v11) = 1;
  *(_QWORD *)&v11 = a2;
  TmpTmNamespace.TableContext = &v11;
  while ( 1 )
  {
    v7 = RtlEnumerateGenericTableLikeADirectory(&TmpTmNamespace, 0, 0, 1u, &RestartKey, &DeleteCount, a2);
    v8 = v7;
    if ( !v7 )
      break;
    v6 = &v7[-(unsigned __int16)word_140007540 - 32];
    if ( !*v7 )
    {
      ObfReferenceObject(&v7[-(unsigned __int16)word_140007540 - 32]);
      if ( (unsigned __int8)TmpFilterTransactionManagerOnlineAndLock(v6, 0) )
        break;
      ObfDereferenceObject(v6);
    }
  }
  if ( v8 )
  {
    *a5 = v6;
    v9 = 0;
  }
  else
  {
    v9 = -2147483622;
  }
  TmpTmNamespace.TableContext = 0;
  KeReleaseMutex(&Mutex, 0);
  return v9;
}

```

## disassembly

```asm
0x14001b960  mov     rax, rsp
0x14001b963  mov     [rax+8], rbx
0x14001b967  mov     [rax+10h], rsi
0x14001b96b  mov     [rax+20h], r9
0x14001b96f  mov     [rax+18h], r8
0x14001b973  push    rdi
0x14001b974  push    r14
0x14001b976  push    r15
0x14001b978  sub     rsp, 60h
0x14001b97c  mov     rbx, rdx
0x14001b97f  lea     r15, TmpTmNamespace
0x14001b986  mov     [rsp+78h+var_38], r15
0x14001b98b  xor     r14d, r14d
0x14001b98e  mov     [rax+18h], r14
0x14001b992  mov     [rax+20h], r14d
0x14001b996  mov     edi, r14d
0x14001b999  xorps   xmm0, xmm0
0x14001b99c  movups  xmmword ptr [rax-28h], xmm0
0x14001b9a0  mov     [rax-58h], r14
0x14001b9a4  xor     r9d, r9d; Alertable
0x14001b9a7  xor     r8d, r8d; WaitMode
0x14001b9aa  xor     edx, edx; WaitReason
0x14001b9ac  lea     rcx, Mutex; Object
0x14001b9b3  call    cs:__imp_KeWaitForSingleObject
0x14001b9ba  nop     dword ptr [rax+rax+00h]
0x14001b9bf  mov     [rsp+78h+var_20], 1
0x14001b9c7  mov     [rsp+78h+var_28], rbx
0x14001b9cc  lea     rax, [rsp+78h+var_28]
0x14001b9d1  mov     cs:TmpTmNamespace.TableContext, rax
0x14001b9d8  mov     [rsp+78h+Buffer], rbx; Buffer
0x14001b9dd  lea     rax, [rsp+78h+arg_18]
0x14001b9e5  mov     [rsp+78h+DeleteCount], rax; DeleteCount
0x14001b9ea  lea     rax, [rsp+78h+arg_10]
0x14001b9f2  mov     [rsp+78h+RestartKey], rax; RestartKey
0x14001b9f7  mov     r9d, 1; NextFlag
0x14001b9fd  xor     r8d, r8d; MatchData
0x14001ba00  xor     edx, edx; MatchFunction
0x14001ba02  mov     rcx, r15; Table
0x14001ba05  call    cs:__imp_RtlEnumerateGenericTableLikeADirectory
0x14001ba0c  nop     dword ptr [rax+rax+00h]
0x14001ba11  mov     rsi, rax
0x14001ba14  test    rax, rax
0x14001ba17  jz      short loc_14001BA53
0x14001ba19  movzx   ecx, cs:word_140007540
0x14001ba20  mov     rdi, rax
0x14001ba23  sub     rdi, rcx
0x14001ba26  sub     rdi, 20h ; ' '
0x14001ba2a  mov     [rsp+78h+var_30], rdi
0x14001ba2f  cmp     byte ptr [rcx+rdi+20h], 0
0x14001ba34  jnz     short loc_14001BA68
0x14001ba36  mov     rcx, rdi; Object
0x14001ba39  call    cs:__imp_ObfReferenceObject
0x14001ba40  nop     dword ptr [rax+rax+00h]
0x14001ba45  xor     edx, edx
0x14001ba47  mov     rcx, rdi
0x14001ba4a  call    TmpFilterTransactionManagerOnlineAndLock
0x14001ba4f  test    al, al
0x14001ba51  jz      short loc_14001BA74
0x14001ba53  test    rsi, rsi
0x14001ba56  jz      short loc_14001BA6D
0x14001ba58  mov     rax, [rsp+78h+arg_20]
0x14001ba60  mov     [rax], rdi
0x14001ba63  mov     ebx, r14d
0x14001ba66  jmp     short loc_14001BA88
0x14001ba68  jmp     loc_14001B9D8
0x14001ba6d  mov     ebx, 8000001Ah
0x14001ba72  jmp     short loc_14001BA88
0x14001ba74  mov     rcx, rdi; Object
0x14001ba77  call    cs:__imp_ObfDereferenceObject
0x14001ba7e  nop     dword ptr [rax+rax+00h]
0x14001ba83  jmp     loc_14001B9D8
0x14001ba88  mov     cs:TmpTmNamespace.TableContext, r14
0x14001ba8f  xor     edx, edx; Wait
0x14001ba91  lea     rcx, Mutex; Mutex
0x14001ba98  call    cs:__imp_KeReleaseMutex
0x14001ba9f  nop     dword ptr [rax+rax+00h]
0x14001baa4  mov     eax, ebx
0x14001baa6  lea     r11, [rsp+78h+var_18]
0x14001baab  mov     rbx, [r11+20h]
0x14001baaf  mov     rsi, [r11+28h]
0x14001bab3  mov     rsp, r11
0x14001bab6  pop     r15
0x14001bab8  pop     r14
0x14001baba  pop     rdi
0x14001babb  retn
0x140021520  push    rbp
0x140021522  sub     rsp, 40h
0x140021526  mov     rbp, rdx
0x140021529  mov     cs:TmpTmNamespace.TableContext, 0
0x140021534  mov     rcx, [rbp+40h]
0x140021538  add     rcx, 68h ; 'h'; Mutex
0x14002153c  xor     edx, edx; Wait
0x14002153e  call    cs:__imp_KeReleaseMutex
0x140021545  nop     dword ptr [rax+rax+00h]
0x14002154a  nop
0x14002154b  add     rsp, 40h
0x14002154f  pop     rbp
0x140021550  retn
```
