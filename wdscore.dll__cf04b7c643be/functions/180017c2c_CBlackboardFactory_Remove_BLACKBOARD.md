# CBlackboardFactory::Remove(_BLACKBOARD *)

- ea: `0x180017c2c`
- end: `0x180017d82`
- name: `?Remove@CBlackboardFactory@@QEAAXPEAU_BLACKBOARD@@@Z`
- size: `342`
- prototype: `void __fastcall(CBlackboardFactory *__hidden this, struct _BLACKBOARD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x180018e90`

## callees

- `0x180002250`
- `0x18000f568`
- `0x18000f9b8`
- `0x180014c68`
- `0x180014d9c`
- `0x180017ab4`
- `0x180017c2c`
- `0x18001dc70`
- `0x18002a010`

## string_xrefs

- `0x180017d2a`: `CBlackboardFactory::Remove`
- `0x180017ce3`: `pBlackboard(0x%x)has %d outstanding access reference count. Client probably did not close Enum handle(s).`

## pseudocode

```c
void __fastcall CBlackboardFactory::Remove(CBlackboardFactory *this, struct _BLACKBOARD *a2)
{
  CBlackboardFactory *v2; // rdi
  struct CBlackboardFactory::SKeeperEntry *Entry; // rax
  int v5; // ecx
  int v6; // ecx
  volatile int *v7; // rsi
  struct CBlackboard *v8; // rdx
  int v9; // ebx
  int *v10; // rax
  unsigned int v11; // edx
  LPCWSTR lpModuleName; // [rsp+88h] [rbp+0h]
  unsigned __int64 v13; // [rsp+90h] [rbp+8h] BYREF

  if ( a2 )
  {
    v2 = Block;
    AcquireWriteAccess((volatile int *)Block);
    if ( (unsigned __int64)a2 >= 0x64 && *((_QWORD *)v2 + 2) > (unsigned __int64)a2 - 100 )
    {
      Entry = CBlackboardFactory::GetEntry(v2, (unsigned __int64)a2 - 100);
      if ( Entry )
      {
        v5 = *((_DWORD *)Entry + 2);
        if ( !v5 || (v6 = v5 - 1, (*((_DWORD *)Entry + 2) = v6) == 0) )
        {
          v7 = *(volatile int **)Entry;
          v8 = *(struct CBlackboard **)Entry;
          *(_QWORD *)Entry = 0;
          if ( !CBlackboardFactory::GetEntry(v2, v8, &v13) )
          {
            if ( *((_DWORD *)v7 + 32) && g_bEnableDiagnosticMode )
            {
              v9 = (**(__int64 (__fastcall ***)(struct IKernel32Interface *))g_Kernel32)(g_Kernel32);
              v10 = (int *)ConstructPartialMsgW(
                             0x67000000u,
                             "pBlackboard(0x%x)has %d outstanding access reference count. Client probably did not close Enum handle(s).",
                             (_DWORD)v7,
                             *((_DWORD *)v7 + 32));
              WdsSetupLogMessageW(
                v10,
                589824,
                (__int64)L"D",
                0,
                0x1C4Eu,
                L"onecore\\base\\ntsetup\\panther\\engine\\bb.cpp",
                L"CBlackboardFactory::Remove",
                lpModuleName,
                v9,
                0,
                0);
            }
            AcquireWriteAccess(v7 + 32);
            ReleaseAccess(v7 + 32);
            if ( v7 )
              CBlackboard::`scalar deleting destructor'((CBlackboard *)v7, v11);
          }
        }
      }
    }
    ReleaseAccess((volatile int *)v2);
  }
}

```

## disassembly

```asm
0x180017c2c  test    rdx, rdx
0x180017c2f  jz      locret_180017D80
0x180017c35  push    rbx
0x180017c36  push    rsi
0x180017c37  push    rdi
0x180017c38  push    r14
0x180017c3a  sub     rsp, 68h
0x180017c3e  mov     rdi, cs:Block
0x180017c45  mov     rbx, rdx
0x180017c48  mov     rcx, rdi; volatile int *
0x180017c4b  call    ?AcquireWriteAccess@@YAXPECJ@Z; AcquireWriteAccess(long volatile *)
0x180017c50  cmp     rbx, 64h ; 'd'
0x180017c54  jb      loc_180017D6F
0x180017c5a  lea     rdx, [rbx-64h]; unsigned __int64
0x180017c5e  cmp     [rdi+10h], rdx
0x180017c62  jbe     loc_180017D6F
0x180017c68  mov     rcx, rdi; this
0x180017c6b  call    ?GetEntry@CBlackboardFactory@@IEAAPEAUSKeeperEntry@1@_K@Z; CBlackboardFactory::GetEntry(unsigned __int64)
0x180017c70  test    rax, rax
0x180017c73  jz      loc_180017D6F
0x180017c79  mov     ecx, [rax+8]
0x180017c7c  test    ecx, ecx
0x180017c7e  jz      short loc_180017C8C
0x180017c80  sub     ecx, 1
0x180017c83  mov     [rax+8], ecx
0x180017c86  jnz     loc_180017D6F
0x180017c8c  mov     rsi, [rax]
0x180017c8f  lea     r8, [rsp+88h+arg_0]; unsigned __int64 *
0x180017c97  mov     rdx, rsi; struct CBlackboard *
0x180017c9a  mov     qword ptr [rax], 0
0x180017ca1  mov     rcx, rdi; this
0x180017ca4  call    ?GetEntry@CBlackboardFactory@@IEAAPEAUSKeeperEntry@1@PEAVCBlackboard@@AEA_K@Z; CBlackboardFactory::GetEntry(CBlackboard *,unsigned __int64 &)
0x180017ca9  test    rax, rax
0x180017cac  jnz     loc_180017D6F
0x180017cb2  lea     r14, [rsi+80h]
0x180017cb9  cmp     [r14], eax
0x180017cbc  jz      loc_180017D52
0x180017cc2  cmp     cs:?g_bEnableDiagnosticMode@@3HA, eax; int g_bEnableDiagnosticMode
0x180017cc8  jz      loc_180017D52
0x180017cce  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180017cd5  mov     rax, [rcx]
0x180017cd8  mov     rax, [rax]
0x180017cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ce0  mov     r9d, [r14]
0x180017ce3  lea     rdx, aPblackboard0xX; "pBlackboard(0x%x)has %d outstanding acc"...
0x180017cea  mov     r8, rsi
0x180017ced  mov     ecx, 67000000h; unsigned int
0x180017cf2  mov     ebx, eax
0x180017cf4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180017cf9  mov     rcx, [rsp+88h]
0x180017d01  lea     r8, aD_1; "D"
0x180017d08  mov     [rsp+88h+var_38], 0; int
0x180017d10  xor     r9d, r9d; int
0x180017d13  mov     [rsp+88h+var_40], 0; __int64
0x180017d1c  mov     edx, 90000h; int
0x180017d21  mov     [rsp+88h+var_48], ebx; int
0x180017d25  mov     [rsp+88h+lpModuleName], rcx; lpModuleName
0x180017d2a  lea     rcx, aCblackboardfac; "CBlackboardFactory::Remove"
0x180017d31  mov     [rsp+88h+var_58], rcx; __int64
0x180017d36  lea     rcx, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\panther\\engine"...
0x180017d3d  mov     [rsp+88h+var_60], rcx; unsigned __int16 *
0x180017d42  mov     rcx, rax; int
0x180017d45  mov     [rsp+88h+var_68], 1C4Eh; int
0x180017d4d  call    WdsSetupLogMessageW
0x180017d52  mov     rcx, r14; volatile int *
0x180017d55  call    ?AcquireWriteAccess@@YAXPECJ@Z; AcquireWriteAccess(long volatile *)
0x180017d5a  mov     rcx, r14; volatile int *
0x180017d5d  call    ?ReleaseAccess@@YAXPECJ@Z; ReleaseAccess(long volatile *)
0x180017d62  test    rsi, rsi
0x180017d65  jz      short loc_180017D6F
0x180017d67  mov     rcx, rsi; this
0x180017d6a  call    ??_GCBlackboard@@QEAAPEAXI@Z; CBlackboard::`scalar deleting destructor'(uint)
0x180017d6f  mov     rcx, rdi; volatile int *
0x180017d72  call    ?ReleaseAccess@@YAXPECJ@Z; ReleaseAccess(long volatile *)
0x180017d77  add     rsp, 68h
0x180017d7b  pop     r14
0x180017d7d  pop     rdi
0x180017d7e  pop     rsi
0x180017d7f  pop     rbx
0x180017d80  retn
```
