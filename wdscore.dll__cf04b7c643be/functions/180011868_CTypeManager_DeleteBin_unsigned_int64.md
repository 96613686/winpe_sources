# CTypeManager::DeleteBin(unsigned __int64)

- ea: `0x180011868`
- end: `0x18001190c`
- name: `?DeleteBin@CTypeManager@@QEAAH_K@Z`
- size: `164`
- prototype: `__int64 __fastcall(CTypeManager *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180011914`
- `0x180011c4c`
- `0x180013b28`

## callees

- `0x180011868`
- `0x180011aa0`
- `0x1800149c4`
- `0x1800151c4`
- `0x180027510`

## pseudocode

```c
__int64 __fastcall CTypeManager::DeleteBin(CTypeManager *this, unsigned __int64 a2)
{
  unsigned __int64 v4; // rax
  unsigned __int64 v5; // r8
  _BYTE v7[400]; // [rsp+30h] [rbp-1A8h] BYREF

  if ( !a2 )
    return 0;
  if ( !(unsigned int)CBinDescriptorTable::Init(
                        (CBinDescriptorTable *)v7,
                        *((_QWORD *)this + 1),
                        *((struct CMemoryManager **)this + 4),
                        (CTypeManager *)((char *)this + 24),
                        0) )
    return 0;
  v4 = CBinDescriptorTable::DeleteID((CBinDescriptorTable *)v7, a2);
  if ( !v4 )
    return 0;
  if ( !(unsigned int)CMemoryManager::Free(*((CMemoryManager **)this + 4), v4, v5) )
  {
    *(_DWORD *)(*((_QWORD *)this + 4) + 32LL) = 1;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180011868  mov     [rsp+arg_10], rbx
0x18001186d  push    rdi
0x18001186e  sub     rsp, 1D0h
0x180011875  mov     rax, cs:__security_cookie
0x18001187c  xor     rax, rsp
0x18001187f  mov     [rsp+1D8h+var_18], rax
0x180011887  mov     rdi, rdx
0x18001188a  mov     rbx, rcx
0x18001188d  test    rdx, rdx
0x180011890  jz      short loc_1800118E1
0x180011892  mov     r8, [rcx+20h]; struct CMemoryManager *
0x180011896  lea     r9, [rcx+18h]; struct CSpinLockFileMappingArray *
0x18001189a  mov     rdx, [rcx+8]; unsigned __int64
0x18001189e  lea     rcx, [rsp+1D8h+var_1A8]; this
0x1800118a3  mov     [rsp+1D8h+var_1B8], 0; int
0x1800118ab  call    ?Init@CBinDescriptorTable@@QEAAH_KPEAVCMemoryManager@@PEAVCSpinLockFileMappingArray@@H@Z; CBinDescriptorTable::Init(unsigned __int64,CMemoryManager *,CSpinLockFileMappingArray *,int)
0x1800118b0  test    eax, eax
0x1800118b2  jz      short loc_1800118E1
0x1800118b4  mov     rdx, rdi; unsigned __int64
0x1800118b7  lea     rcx, [rsp+1D8h+var_1A8]; this
0x1800118bc  call    ?DeleteID@CBinDescriptorTable@@QEAA_K_K@Z; CBinDescriptorTable::DeleteID(unsigned __int64)
0x1800118c1  test    rax, rax
0x1800118c4  jz      short loc_1800118E1
0x1800118c6  mov     rcx, [rbx+20h]; this
0x1800118ca  mov     rdx, rax; unsigned __int64
0x1800118cd  call    ?Free@CMemoryManager@@QEAAH_K0@Z; CMemoryManager::Free(unsigned __int64,unsigned __int64)
0x1800118d2  test    eax, eax
0x1800118d4  jnz     short loc_180011905
0x1800118d6  mov     rax, [rbx+20h]
0x1800118da  mov     dword ptr [rax+20h], 1
0x1800118e1  xor     eax, eax
0x1800118e3  mov     rcx, [rsp+1D8h+var_18]
0x1800118eb  xor     rcx, rsp; StackCookie
0x1800118ee  call    __security_check_cookie
0x1800118f3  mov     rbx, [rsp+1D8h+arg_10]
0x1800118fb  add     rsp, 1D0h
0x180011902  pop     rdi
0x180011903  retn
0x180011905  mov     eax, 1
0x18001190a  jmp     short loc_1800118E3
```
