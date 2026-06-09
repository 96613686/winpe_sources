# CWerComSupportClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000a650`
- end: `0x18000a78d`
- name: `?CreateInstance@CWerComSupportClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `317`
- prototype: `__int64 __fastcall(CWerComSupportClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001634`
- `0x180002850`
- `0x180006c9c`
- `0x1800073d4`
- `0x18000a650`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall CWerComSupportClassFactory::CreateInstance(
        CWerComSupportClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v6; // ebx
  CManagedObj *v7; // rax
  CManagedObj *v8; // rdi

  *a4 = 0;
  if ( a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
    return (unsigned int)-2147221232;
  }
  else
  {
    v7 = (CManagedObj *)operator new(0x28u);
    v8 = v7;
    if ( v7 )
    {
      CManagedObj::CManagedObj(v7);
      *((_QWORD *)v8 + 4) = 0;
      *(_QWORD *)v8 = &CWerComStoreFactory::`vftable'{for `CManagedObj'};
      *((_QWORD *)v8 + 3) = &CWerComStoreFactory::`vftable'{for `IWerStoreFactory'};
      _InterlockedIncrement((volatile signed __int32 *)v8 + 2);
      v6 = (**(__int64 (__fastcall ***)(CManagedObj *, const struct _GUID *, void **))v8)(v8, a3, a4);
      if ( v6 >= 0 )
      {
        v6 = 0;
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          115,
          WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids,
          (unsigned int)v6);
      }
      (*(void (__fastcall **)(CManagedObj *))(*(_QWORD *)v8 + 16LL))(v8);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000a650  mov     [rsp+arg_0], rbx
0x18000a655  mov     [rsp+arg_8], rsi
0x18000a65a  push    rdi
0x18000a65b  sub     rsp, 20h
0x18000a65f  mov     qword ptr [r9], 0
0x18000a666  mov     rbx, r9
0x18000a669  mov     rsi, r8
0x18000a66c  test    rdx, rdx
0x18000a66f  jz      short loc_18000A6A9
0x18000a671  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a678  lea     rax, WPP_GLOBAL_Control
0x18000a67f  cmp     rcx, rax
0x18000a682  jz      short loc_18000A69F
0x18000a684  test    byte ptr [rcx+1Ch], 1
0x18000a688  jz      short loc_18000A69F
0x18000a68a  mov     rcx, [rcx+10h]
0x18000a68e  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000a695  mov     edx, 71h ; 'q'
0x18000a69a  call    WPP_SF_
0x18000a69f  mov     ebx, 80040110h
0x18000a6a4  jmp     loc_18000A77B
0x18000a6a9  mov     ecx, 28h ; '('; Size
0x18000a6ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a6b3  mov     rdi, rax
0x18000a6b6  test    rax, rax
0x18000a6b9  jz      loc_18000A748
0x18000a6bf  mov     rcx, rax; this
0x18000a6c2  call    ??0CManagedObj@@QEAA@XZ; CManagedObj::CManagedObj(void)
0x18000a6c7  lea     rax, ??_7CWerComStoreFactory@@6BCManagedObj@@@; const CWerComStoreFactory::`vftable'{for `CManagedObj'}
0x18000a6ce  mov     qword ptr [rdi+20h], 0
0x18000a6d6  mov     [rdi], rax
0x18000a6d9  lea     rax, ??_7CWerComStoreFactory@@6BIWerStoreFactory@@@; const CWerComStoreFactory::`vftable'{for `IWerStoreFactory'}
0x18000a6e0  mov     [rdi+18h], rax
0x18000a6e4  lock inc dword ptr [rdi+8]
0x18000a6e8  mov     rax, [rdi]
0x18000a6eb  mov     r8, rbx
0x18000a6ee  mov     rdx, rsi
0x18000a6f1  mov     rcx, rdi
0x18000a6f4  mov     rax, [rax]
0x18000a6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6fc  mov     ebx, eax
0x18000a6fe  test    eax, eax
0x18000a700  jns     short loc_18000A735
0x18000a702  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a709  lea     rax, WPP_GLOBAL_Control
0x18000a710  cmp     rcx, rax
0x18000a713  jz      short loc_18000A737
0x18000a715  test    byte ptr [rcx+1Ch], 1
0x18000a719  jz      short loc_18000A737
0x18000a71b  mov     rcx, [rcx+10h]
0x18000a71f  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000a726  mov     edx, 73h ; 's'
0x18000a72b  mov     r9d, ebx
0x18000a72e  call    WPP_SF_d
0x18000a733  jmp     short loc_18000A737
0x18000a735  xor     ebx, ebx
0x18000a737  mov     rax, [rdi]
0x18000a73a  mov     rcx, rdi
0x18000a73d  mov     rax, [rax+10h]
0x18000a741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a746  jmp     short loc_18000A77B
0x18000a748  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a74f  lea     rax, WPP_GLOBAL_Control
0x18000a756  cmp     rcx, rax
0x18000a759  jz      short loc_18000A776
0x18000a75b  test    byte ptr [rcx+1Ch], 1
0x18000a75f  jz      short loc_18000A776
0x18000a761  mov     rcx, [rcx+10h]
0x18000a765  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000a76c  mov     edx, 72h ; 'r'
0x18000a771  call    WPP_SF_
0x18000a776  mov     ebx, 8007000Eh
0x18000a77b  mov     rsi, [rsp+28h+arg_8]
0x18000a780  mov     eax, ebx
0x18000a782  mov     rbx, [rsp+28h+arg_0]
0x18000a787  add     rsp, 20h
0x18000a78b  pop     rdi
0x18000a78c  retn
```
