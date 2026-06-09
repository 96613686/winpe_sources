# PMH_LISTENER_CHANNEL_CALLBACK::GetBlobLength(ulong *)

- ea: `0x180003360`
- end: `0x1800033e0`
- name: `?GetBlobLength@PMH_LISTENER_CHANNEL_CALLBACK@@UEAAJPEAK@Z`
- size: `128`
- prototype: `__int64 __fastcall(PMH_LISTENER_CHANNEL_CALLBACK *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003360`
- `0x180005010`

## import_xrefs

- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180003384`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180003384`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800033c8`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800033c8`

## pseudocode

```c
__int64 __fastcall PMH_LISTENER_CHANNEL_CALLBACK::GetBlobLength(PMH_LISTENER_CHANNEL_CALLBACK *this, unsigned int *a2)
{
  CReaderWriterLock3 *v2; // rdi
  __int64 v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // ebx
  unsigned int v9; // [rsp+30h] [rbp+8h] BYREF

  v2 = (PMH_LISTENER_CHANNEL_CALLBACK *)((char *)this + 8);
  v9 = 0;
  CReaderWriterLock3::ReadLock((PMH_LISTENER_CHANNEL_CALLBACK *)((char *)this + 8));
  v5 = *((_QWORD *)this + 3);
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v5 + 48LL))(v5, 0, &v9);
    v7 = v6;
    *a2 = v9;
    if ( v6 == -2147024662 || v6 == -2147024774 )
      v7 = 0;
  }
  else
  {
    v7 = -2147467259;
  }
  CReaderWriterLock3::ReadUnlock(v2);
  return v7;
}

```

## disassembly

```asm
0x180003360  mov     [rsp+arg_8], rbx
0x180003365  mov     [rsp+arg_10], rsi
0x18000336a  push    rdi
0x18000336b  sub     rsp, 20h
0x18000336f  lea     rdi, [rcx+8]
0x180003373  mov     [rsp+28h+arg_0], 0
0x18000337b  mov     rbx, rcx
0x18000337e  mov     rsi, rdx
0x180003381  mov     rcx, rdi
0x180003384  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000338a  mov     rcx, [rbx+18h]
0x18000338e  test    rcx, rcx
0x180003391  jz      short loc_1800033C0
0x180003393  mov     rax, [rcx]
0x180003396  lea     r8, [rsp+28h+arg_0]
0x18000339b  xor     edx, edx
0x18000339d  mov     rax, [rax+30h]
0x1800033a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033a6  mov     ecx, [rsp+28h+arg_0]
0x1800033aa  mov     ebx, eax
0x1800033ac  mov     [rsi], ecx
0x1800033ae  cmp     eax, 800700EAh
0x1800033b3  jz      short loc_1800033BC
0x1800033b5  cmp     eax, 8007007Ah
0x1800033ba  jnz     short loc_1800033C5
0x1800033bc  xor     ebx, ebx
0x1800033be  jmp     short loc_1800033C5
0x1800033c0  mov     ebx, 80004005h
0x1800033c5  mov     rcx, rdi
0x1800033c8  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800033ce  mov     rsi, [rsp+28h+arg_10]
0x1800033d3  mov     eax, ebx
0x1800033d5  mov     rbx, [rsp+28h+arg_8]
0x1800033da  add     rsp, 20h
0x1800033de  pop     rdi
0x1800033df  retn
```
