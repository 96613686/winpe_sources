# SecMgrPreAssociateCompletion(API_CONTEXT_BASE *)

- ea: `0x18001d72c`
- end: `0x18001d8a5`
- name: `?SecMgrPreAssociateCompletion@@YAKPEAUAPI_CONTEXT_BASE@@@Z`
- size: `377`
- prototype: `unsigned int __fastcall(struct API_CONTEXT_BASE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001d400`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180011030`
- `0x18001d72c`
- `0x18001d8ac`
- `0x180055a38`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18001d7a7`
- `MobileNetworking!ReleaseWriteLock` at `0x18001d7a7`

## string_xrefs

- `0x18001d79d`: `SecMgrPreAssociateCompletion`

## pseudocode

```c
__int64 __fastcall SecMgrPreAssociateCompletion(struct API_CONTEXT_BASE *a1, __int64 a2, int a3)
{
  struct MSMSEC_INTF_CONTEXT *v4; // rdi
  unsigned int v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // eax
  int v8; // r8d
  PVOID *v9; // rcx
  PVOID *v10; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 119, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
  v4 = (struct MSMSEC_INTF_CONTEXT *)*((_QWORD *)a1 + 1);
  v5 = SecMgrLockAndCheckAdapterDeleted(v4, a2, a3);
  v6 = v5;
  if ( !v5 )
  {
    v7 = SecMgrPreAssociateCompletionLocked(a1);
    v6 = v7;
    if ( v7 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
LABEL_8:
        ReleaseWriteLock(v4, (char *)v4 + 2512, "SecMgrPreAssociateCompletion", 1944);
LABEL_9:
        v10 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_10;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      {
LABEL_5:
        if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x100) != 0 )
          WPP_SF_Ls((unsigned int)v9[7], 11, v8, *((_DWORD *)v4 + 624), (__int64)"<<< Unlocking <<<");
        goto LABEL_8;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 121, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v7);
    }
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_5;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 120, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v5);
    goto LABEL_9;
  }
LABEL_10:
  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x100) != 0 )
    WPP_SF_d(v10[7], 122, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18001d72c  push    rbx
0x18001d72e  push    rbp
0x18001d72f  push    rsi
0x18001d730  push    rdi
0x18001d731  sub     rsp, 38h
0x18001d735  mov     rsi, rcx
0x18001d738  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d73f  lea     rbp, WPP_GLOBAL_Control
0x18001d746  cmp     rcx, rbp
0x18001d749  jnz     loc_18001D7D8
0x18001d74f  mov     rdi, [rsi+8]
0x18001d753  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x18001d756  call    ?SecMgrLockAndCheckAdapterDeleted@@YAKPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrLockAndCheckAdapterDeleted(MSMSEC_INTF_CONTEXT *)
0x18001d75b  mov     ebx, eax
0x18001d75d  test    eax, eax
0x18001d75f  jnz     loc_18001D7FF
0x18001d765  mov     rcx, rsi; struct API_CONTEXT_BASE *
0x18001d768  call    ?SecMgrPreAssociateCompletionLocked@@YAKPEAUAPI_CONTEXT_BASE@@@Z; SecMgrPreAssociateCompletionLocked(API_CONTEXT_BASE *)
0x18001d76d  mov     ebx, eax
0x18001d76f  test    eax, eax
0x18001d771  jnz     loc_18001D82B
0x18001d777  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d77e  cmp     rcx, rbp
0x18001d781  jz      short loc_18001D790
0x18001d783  test    dword ptr [rcx+44h], 100h
0x18001d78a  jnz     loc_18001D862
0x18001d790  lea     rdx, [rdi+9D0h]
0x18001d797  mov     r9d, 798h
0x18001d79d  lea     r8, aSecmgrpreassoc; "SecMgrPreAssociateCompletion"
0x18001d7a4  mov     rcx, rdi
0x18001d7a7  call    cs:__imp_ReleaseWriteLock
0x18001d7ae  nop     dword ptr [rax+rax+00h]
0x18001d7b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d7ba  cmp     rcx, rbp
0x18001d7bd  jz      short loc_18001D7CC
0x18001d7bf  test    dword ptr [rcx+44h], 100h
0x18001d7c6  jnz     loc_18001D888
0x18001d7cc  mov     eax, ebx
0x18001d7ce  add     rsp, 38h
0x18001d7d2  pop     rdi
0x18001d7d3  pop     rsi
0x18001d7d4  pop     rbp
0x18001d7d5  pop     rbx
0x18001d7d6  retn
0x18001d7d8  test    dword ptr [rcx+44h], 100h
0x18001d7df  jz      loc_18001D74F
0x18001d7e5  mov     rcx, [rcx+38h]
0x18001d7e9  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x18001d7f0  mov     edx, 77h ; 'w'
0x18001d7f5  call    WPP_SF_
0x18001d7fa  jmp     loc_18001D74F
0x18001d7ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d806  cmp     rcx, rbp
0x18001d809  jz      short loc_18001D7CC
0x18001d80b  test    byte ptr [rcx+44h], 1
0x18001d80f  jz      short loc_18001D7BA
0x18001d811  mov     rcx, [rcx+38h]
0x18001d815  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x18001d81c  mov     edx, 78h ; 'x'
0x18001d821  mov     r9d, eax
0x18001d824  call    WPP_SF_d
0x18001d829  jmp     short loc_18001D7B3
0x18001d82b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d832  cmp     rcx, rbp
0x18001d835  jz      loc_18001D790
0x18001d83b  test    byte ptr [rcx+44h], 1
0x18001d83f  jz      loc_18001D77E
0x18001d845  mov     rcx, [rcx+38h]
0x18001d849  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x18001d850  mov     edx, 79h ; 'y'
0x18001d855  mov     r9d, eax
0x18001d858  call    WPP_SF_d
0x18001d85d  jmp     loc_18001D777
0x18001d862  mov     r9d, [rdi+9C0h]
0x18001d869  lea     rax, aUnlocking; "<<< Unlocking <<<"
0x18001d870  mov     rcx, [rcx+38h]
0x18001d874  mov     edx, 0Bh
0x18001d879  mov     [rsp+58h+var_38], rax
0x18001d87e  call    WPP_SF_Ls
0x18001d883  jmp     loc_18001D790
0x18001d888  mov     rcx, [rcx+38h]
0x18001d88c  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x18001d893  mov     edx, 7Ah ; 'z'
0x18001d898  mov     r9d, ebx
0x18001d89b  call    WPP_SF_d
0x18001d8a0  jmp     loc_18001D7CC
```
