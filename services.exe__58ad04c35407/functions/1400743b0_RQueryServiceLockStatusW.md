# RQueryServiceLockStatusW

- ea: `0x1400743b0`
- end: `0x1400745af`
- name: `RQueryServiceLockStatusW`
- size: `511`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x140075520`

## callees

- `0x1400083f0`
- `0x14000ab50`
- `0x140017160`
- `0x14002530c`
- `0x140073e2c`
- `0x1400743b0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400744f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400744f9`
- `ntdll!RtlReleaseResource` at `0x14007458f`
- `ntdll!RtlReleaseResource` at `0x14007458f`
- `ntdll!RtlAcquireResourceShared` at `0x140074427`
- `ntdll!RtlAcquireResourceShared` at `0x140074427`
- `ntdll!RtlAreAllAccessesGranted` at `0x14007440a`
- `ntdll!RtlAreAllAccessesGranted` at `0x14007440a`
- `ntdll!RtlFreeHeap` at `0x1400744e0`
- `ntdll!RtlFreeHeap` at `0x14007457f`
- `ntdll!RtlFreeHeap` at `0x1400744e0`
- `ntdll!RtlFreeHeap` at `0x14007457f`

## pseudocode

```c
__int64 __fastcall RQueryServiceLockStatusW(void *a1, __int64 a2, unsigned int a3, unsigned int *a4)
{
  struct _API_LOCK *ApiLockForDatabase; // rax
  struct _API_LOCK *v10; // rbp
  ULONG LockOwner; // ebx
  unsigned __int16 *v12; // rsi
  __int64 v13; // rbx
  __int64 v14; // rax
  unsigned int v15; // r15d
  unsigned int v16; // ebp
  DWORD TickCount; // r8d
  unsigned int v18; // ecx
  PVOID P; // [rsp+80h] [rbp+8h] BYREF

  P = 0;
  ScSetTcpKeepalive();
  if ( !(unsigned int)ScIsValidScManagerHandle(a1) )
    return 6;
  if ( a2 && a4 )
  {
    if ( !RtlAreAllAccessesGranted(*((_DWORD *)a1 + 2), 0x10u) )
      return 5;
    RtlAcquireResourceShared(&ScServiceRecordLock, 1u);
    ApiLockForDatabase = ScFindApiLockForDatabase(*((wchar_t **)a1 + 2));
    v10 = ApiLockForDatabase;
    if ( ApiLockForDatabase )
    {
      LockOwner = ScGetLockOwner(*((void **)ApiLockForDatabase + 5), (unsigned __int16 **)&P);
      if ( LockOwner )
      {
LABEL_23:
        RtlReleaseResource(&ScServiceRecordLock);
        return LockOwner;
      }
      v12 = (unsigned __int16 *)P;
      v13 = -1;
      v14 = -1;
      do
        ++v14;
      while ( *((_WORD *)P + v14) );
      v15 = 2 * v14 + 26;
      *a4 = v15;
      if ( v15 <= a3 )
      {
        *(_DWORD *)a2 = 1;
        v16 = *((_DWORD *)v10 + 8);
        TickCount = GetTickCount();
        if ( TickCount >= v16 )
          v18 = (TickCount - v16) / 0x3E8;
        else
          v18 = TickCount / 0x3E8 + ~v16 / 0x3E8;
        *(_DWORD *)(a2 + 16) = v18;
        P = (PVOID)(a2 + v15);
        do
          ++v13;
        while ( v12[v13] );
        ScCopyStringToBufferW(
          v12,
          v13,
          (const unsigned __int16 *)(a2 + 24),
          (unsigned __int16 **)&P,
          (unsigned __int16 **)(a2 + 8),
          0);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
        goto LABEL_22;
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
    }
    else
    {
      *a4 = 26;
      if ( a3 >= 0x1A )
      {
        P = (PVOID)(a2 + 26);
        *(_DWORD *)a2 = 0;
        ScCopyStringToBufferW(
          0,
          0,
          (const unsigned __int16 *)(a2 + 24),
          (unsigned __int16 **)&P,
          (unsigned __int16 **)(a2 + 8),
          0);
        *(_DWORD *)(a2 + 16) = 0;
LABEL_22:
        LockOwner = 0;
        goto LABEL_23;
      }
    }
    LockOwner = 122;
    goto LABEL_23;
  }
  return 87;
}

```

## disassembly

```asm
0x1400743b0  mov     rax, rsp
0x1400743b3  push    rbx
0x1400743b4  push    rbp
0x1400743b5  push    rsi
0x1400743b6  push    rdi
0x1400743b7  push    r12
0x1400743b9  push    r13
0x1400743bb  push    r14
0x1400743bd  push    r15
0x1400743bf  sub     rsp, 38h
0x1400743c3  xor     r13d, r13d
0x1400743c6  mov     r14, r9
0x1400743c9  mov     [rax+8], r13
0x1400743cd  mov     r12d, r8d
0x1400743d0  mov     rdi, rdx
0x1400743d3  mov     rbx, rcx
0x1400743d6  call    ?ScSetTcpKeepalive@@YAXXZ; ScSetTcpKeepalive(void)
0x1400743db  mov     rcx, rbx; void *
0x1400743de  call    ?ScIsValidScManagerHandle@@YAHPEAX@Z; ScIsValidScManagerHandle(void *)
0x1400743e3  test    eax, eax
0x1400743e5  jnz     short loc_1400743F0
0x1400743e7  lea     eax, [r13+6]
0x1400743eb  jmp     loc_14007459E
0x1400743f0  test    rdi, rdi
0x1400743f3  jz      loc_140074599
0x1400743f9  test    r14, r14
0x1400743fc  jz      loc_140074599
0x140074402  mov     ecx, [rbx+8]; GrantedAccess
0x140074405  mov     edx, 10h; DesiredAccess
0x14007440a  call    cs:__imp_RtlAreAllAccessesGranted
0x140074410  test    al, al
0x140074412  jnz     short loc_14007441E
0x140074414  mov     eax, 5
0x140074419  jmp     loc_14007459E
0x14007441e  mov     dl, 1; Wait
0x140074420  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140074427  call    cs:__imp_RtlAcquireResourceShared
0x14007442d  mov     rcx, [rbx+10h]; String1
0x140074431  call    ?ScFindApiLockForDatabase@@YAPEAU_API_LOCK@@PEAG@Z; ScFindApiLockForDatabase(ushort *)
0x140074436  mov     rbp, rax
0x140074439  test    rax, rax
0x14007443c  jnz     short loc_14007448A
0x14007443e  mov     dword ptr [r14], 1Ah
0x140074445  cmp     r12d, 1Ah
0x140074449  jb      loc_1400744E6
0x14007444f  lea     rax, [rdi+1Ah]
0x140074453  mov     [rsp+78h+var_50], r13; unsigned __int8 *
0x140074458  mov     [rsp+78h+P], rax
0x140074460  lea     r8, [rdi+18h]; unsigned __int16 *
0x140074464  lea     rax, [rdi+8]
0x140074468  mov     [rdi], r13d
0x14007446b  lea     r9, [rsp+78h+P]; unsigned __int16 **
0x140074473  mov     [rsp+78h+var_58], rax; unsigned __int16 **
0x140074478  xor     edx, edx; unsigned int
0x14007447a  xor     ecx, ecx; unsigned __int16 *
0x14007447c  call    ?ScCopyStringToBufferW@@YAHPEBGK0PEAPEAG1QEAE@Z; ScCopyStringToBufferW(ushort const *,ulong,ushort const *,ushort * *,ushort * *,uchar * const)
0x140074481  mov     [rdi+10h], r13d
0x140074485  jmp     loc_140074585
0x14007448a  mov     rcx, [rax+28h]; void *
0x14007448e  lea     rdx, [rsp+78h+P]; unsigned __int16 **
0x140074496  call    ?ScGetLockOwner@@YAKPEAXPEAPEAG@Z; ScGetLockOwner(void *,ushort * *)
0x14007449b  mov     ebx, eax
0x14007449d  test    eax, eax
0x14007449f  jnz     loc_140074588
0x1400744a5  mov     rsi, [rsp+78h+P]
0x1400744ad  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400744b1  mov     rax, rbx
0x1400744b4  inc     rax
0x1400744b7  cmp     [rsi+rax*2], r13w
0x1400744bc  jnz     short loc_1400744B4
0x1400744be  lea     r15d, ds:1Ah[rax*2]
0x1400744c6  mov     [r14], r15d
0x1400744c9  cmp     r15d, r12d
0x1400744cc  jbe     short loc_1400744F0
0x1400744ce  mov     rcx, gs:60h
0x1400744d7  mov     r8, rsi; P
0x1400744da  xor     edx, edx; Flags
0x1400744dc  mov     rcx, [rcx+30h]; HeapHandle
0x1400744e0  call    cs:__imp_RtlFreeHeap
0x1400744e6  mov     ebx, 7Ah ; 'z'
0x1400744eb  jmp     loc_140074588
0x1400744f0  mov     dword ptr [rdi], 1
0x1400744f6  mov     ebp, [rbp+20h]
0x1400744f9  call    cs:__imp_GetTickCount
0x1400744ff  mov     r8d, eax
0x140074502  cmp     eax, ebp
0x140074504  mov     eax, 10624DD3h
0x140074509  jnb     short loc_140074523
0x14007450b  not     ebp
0x14007450d  mul     ebp
0x14007450f  mov     eax, 10624DD3h
0x140074514  mov     ecx, edx
0x140074516  mul     r8d
0x140074519  shr     ecx, 6
0x14007451c  shr     edx, 6
0x14007451f  add     ecx, edx
0x140074521  jmp     short loc_14007452E
0x140074523  sub     r8d, ebp
0x140074526  mul     r8d
0x140074529  mov     ecx, edx
0x14007452b  shr     ecx, 6
0x14007452e  mov     eax, r15d
0x140074531  add     rax, rdi
0x140074534  mov     [rdi+10h], ecx
0x140074537  mov     [rsp+78h+P], rax
0x14007453f  inc     rbx
0x140074542  cmp     [rsi+rbx*2], r13w
0x140074547  jnz     short loc_14007453F
0x140074549  lea     rax, [rdi+8]
0x14007454d  mov     [rsp+78h+var_50], r13; unsigned __int8 *
0x140074552  lea     r8, [rdi+18h]; unsigned __int16 *
0x140074556  mov     [rsp+78h+var_58], rax; unsigned __int16 **
0x14007455b  lea     r9, [rsp+78h+P]; unsigned __int16 **
0x140074563  mov     edx, ebx; unsigned int
0x140074565  mov     rcx, rsi; unsigned __int16 *
0x140074568  call    ?ScCopyStringToBufferW@@YAHPEBGK0PEAPEAG1QEAE@Z; ScCopyStringToBufferW(ushort const *,ulong,ushort const *,ushort * *,ushort * *,uchar * const)
0x14007456d  mov     rcx, gs:60h
0x140074576  mov     r8, rsi; P
0x140074579  xor     edx, edx; Flags
0x14007457b  mov     rcx, [rcx+30h]; HeapHandle
0x14007457f  call    cs:__imp_RtlFreeHeap
0x140074585  mov     ebx, r13d
0x140074588  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x14007458f  call    cs:__imp_RtlReleaseResource
0x140074595  mov     eax, ebx
0x140074597  jmp     short loc_14007459E
0x140074599  mov     eax, 57h ; 'W'
0x14007459e  add     rsp, 38h
0x1400745a2  pop     r15
0x1400745a4  pop     r14
0x1400745a6  pop     r13
0x1400745a8  pop     r12
0x1400745aa  pop     rdi
0x1400745ab  pop     rsi
0x1400745ac  pop     rbp
0x1400745ad  pop     rbx
0x1400745ae  retn
```
