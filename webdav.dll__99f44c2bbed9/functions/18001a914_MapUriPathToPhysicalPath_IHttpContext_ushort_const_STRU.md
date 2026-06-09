# MapUriPathToPhysicalPath(IHttpContext *,ushort const *,STRU *)

- ea: `0x18001a914`
- end: `0x18001a9f2`
- name: `?MapUriPathToPhysicalPath@@YAJPEAVIHttpContext@@PEBGPEAVSTRU@@@Z`
- size: `222`
- prototype: `int(struct IHttpContext *, const unsigned __int16 *, struct STRU *)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002740`
- `0x18000579c`
- `0x180006940`
- `0x180010d20`

## callees

- `0x180019ff8`
- `0x18001a914`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x18001a947`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001a947`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001a9d0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001a9d0`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001a9b3`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001a9b3`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18001a980`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18001a980`

## pseudocode

```c
__int64 __fastcall MapUriPathToPhysicalPath(struct IHttpContext *a1, const unsigned __int16 *a2, struct STRU *a3)
{
  __int64 v6; // rax
  int CanonicalizationProofPhysicalPath; // ebx
  unsigned int v9; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v10[32]; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int16 *v11; // [rsp+58h] [rbp-28h]

  v9 = 0;
  STRU::STRU((STRU *)v10);
  v6 = *(_QWORD *)a1;
  v9 = 0;
  CanonicalizationProofPhysicalPath = (*(__int64 (__fastcall **)(struct IHttpContext *, const unsigned __int16 *, _QWORD, unsigned int *))(v6 + 216))(
                                        a1,
                                        a2,
                                        0,
                                        &v9);
  if ( CanonicalizationProofPhysicalPath == -2147024774 )
  {
    CanonicalizationProofPhysicalPath = STRU::Resize((STRU *)v10, v9);
    if ( CanonicalizationProofPhysicalPath >= 0 )
    {
      CanonicalizationProofPhysicalPath = (*(__int64 (__fastcall **)(struct IHttpContext *, const unsigned __int16 *, unsigned __int16 *, unsigned int *))(*(_QWORD *)a1 + 216LL))(
                                            a1,
                                            a2,
                                            v11,
                                            &v9);
      if ( CanonicalizationProofPhysicalPath >= 0 )
      {
        STRU::SyncWithBuffer((STRU *)v10);
        CanonicalizationProofPhysicalPath = GetCanonicalizationProofPhysicalPath(v11, 1, a3);
      }
    }
  }
  STRU::~STRU((STRU *)v10);
  return (unsigned int)CanonicalizationProofPhysicalPath;
}

```

## disassembly

```asm
0x18001a914  push    rbp
0x18001a916  push    rbx
0x18001a917  push    rsi
0x18001a918  push    rdi
0x18001a919  push    r14
0x18001a91b  mov     rbp, rsp
0x18001a91e  sub     rsp, 80h
0x18001a925  mov     rax, cs:__security_cookie
0x18001a92c  xor     rax, rsp
0x18001a92f  mov     [rbp+var_10], rax
0x18001a933  mov     rdi, rcx
0x18001a936  mov     [rbp+var_50], 0
0x18001a93d  lea     rcx, [rbp+var_48]
0x18001a941  mov     rsi, r8
0x18001a944  mov     r14, rdx
0x18001a947  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001a94d  mov     rax, [rdi]
0x18001a950  lea     r9, [rbp+var_50]
0x18001a954  xor     r8d, r8d
0x18001a957  mov     [rbp+var_50], 0
0x18001a95e  mov     rdx, r14
0x18001a961  mov     rcx, rdi
0x18001a964  mov     rax, [rax+0D8h]
0x18001a96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a970  lea     rcx, [rbp+var_48]
0x18001a974  mov     ebx, eax
0x18001a976  cmp     eax, 8007007Ah
0x18001a97b  jnz     short loc_18001A9D0
0x18001a97d  mov     edx, [rbp+var_50]
0x18001a980  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x18001a986  mov     ebx, eax
0x18001a988  test    eax, eax
0x18001a98a  js      short loc_18001A9CC
0x18001a98c  mov     rax, [rdi]
0x18001a98f  lea     r9, [rbp+var_50]
0x18001a993  mov     r8, [rbp+var_28]
0x18001a997  mov     rdx, r14
0x18001a99a  mov     rcx, rdi
0x18001a99d  mov     rax, [rax+0D8h]
0x18001a9a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9a9  mov     ebx, eax
0x18001a9ab  test    eax, eax
0x18001a9ad  js      short loc_18001A9CC
0x18001a9af  lea     rcx, [rbp+var_48]
0x18001a9b3  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18001a9b9  mov     rcx, [rbp+var_28]; unsigned __int16 *
0x18001a9bd  mov     r8, rsi; struct STRU *
0x18001a9c0  mov     edx, 1; int
0x18001a9c5  call    ?GetCanonicalizationProofPhysicalPath@@YAJPEBGHPEAVSTRU@@@Z; GetCanonicalizationProofPhysicalPath(ushort const *,int,STRU *)
0x18001a9ca  mov     ebx, eax
0x18001a9cc  lea     rcx, [rbp+var_48]
0x18001a9d0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001a9d6  mov     eax, ebx
0x18001a9d8  mov     rcx, [rbp+var_10]
0x18001a9dc  xor     rcx, rsp; StackCookie
0x18001a9df  call    __security_check_cookie
0x18001a9e4  add     rsp, 80h
0x18001a9eb  pop     r14
0x18001a9ed  pop     rdi
0x18001a9ee  pop     rsi
0x18001a9ef  pop     rbx
0x18001a9f0  pop     rbp
0x18001a9f1  retn
```
