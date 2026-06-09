# SecMgrMarkDeletedAndDerefAdapter(MSMSEC_INTF_CONTEXT *)

- ea: `0x180003c78`
- end: `0x180003e79`
- name: `?SecMgrMarkDeletedAndDerefAdapter@@YAKPEAUMSMSEC_INTF_CONTEXT@@@Z`
- size: `513`
- prototype: `unsigned int __fastcall(struct MSMSEC_INTF_CONTEXT *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180003b78`
- `0x18003cefc`

## callees

- `0x180003c78`
- `0x180004518`
- `0x18000892c`
- `0x180008998`
- `0x180011030`
- `0x180013bc0`
- `0x1800169c0`
- `0x180041dac`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003e68`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003e68`
- `MobileNetworking!ReleaseWriteLock` at `0x180003dae`
- `MobileNetworking!ReleaseWriteLock` at `0x180003dae`

## string_xrefs

- `0x180003da4`: `SecMgrMarkDeletedAndDerefAdapter`
- `0x180003ddc`: `SecMgrMarkDeletedAndDerefAdapter`

## pseudocode

```c
__int64 __fastcall SecMgrMarkDeletedAndDerefAdapter(struct MSMSEC_INTF_CONTEXT *a1, __int64 a2, int a3)
{
  PVOID *v4; // rcx
  unsigned int v5; // esi
  unsigned int v7; // eax
  unsigned int v8; // ecx

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 36, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v7 = SecMgrLockAndCheckAdapterDeleted(a1, a2, a3);
    v5 = v7;
    if ( v7 )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v5;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_18;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 38, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v7);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
        WPP_SF_qDDDDDD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          39,
          *((unsigned __int8 *)a1 + 2364),
          a1,
          *((unsigned __int8 *)a1 + 2360),
          *((unsigned __int8 *)a1 + 2361),
          *((unsigned __int8 *)a1 + 2362),
          *((unsigned __int8 *)a1 + 2363),
          *((unsigned __int8 *)a1 + 2364),
          *((unsigned __int8 *)a1 + 2365));
      PreAuthPreDestroyAdapter((struct MSMSEC_INTF_CONTEXT *)((char *)a1 + 2912));
      v8 = *((_DWORD *)a1 + 624);
      *((_DWORD *)a1 + 654) = 1;
      TraceAdapterId(v8, "<<< Unlocking <<<");
      ReleaseWriteLock(a1, (char *)a1 + 2512, "SecMgrMarkDeletedAndDerefAdapter", 586);
      while ( *((int *)a1 + 4) > 1 )
        Sleep(0x64u);
      TraceAdapterId(*((_DWORD *)a1 + 624), "<<< Derefing <<<");
      SecMgrDerefAdapterEx(a1, "SecMgrMarkDeletedAndDerefAdapter", 602);
    }
    goto LABEL_17;
  }
  v5 = 87;
  if ( v4 == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)v4 + 68) & 1) != 0 )
  {
    WPP_SF_(v4[7], 37, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
LABEL_17:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_18:
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x100) != 0 )
    WPP_SF_d(v4[7], 40, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180003c78  push    rbx
0x180003c7a  push    rbp
0x180003c7b  push    rsi
0x180003c7c  push    rdi
0x180003c7d  sub     rsp, 58h
0x180003c81  mov     rdi, rcx
0x180003c84  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c8b  lea     rbp, WPP_GLOBAL_Control
0x180003c92  cmp     rcx, rbp
0x180003c95  jz      short loc_180003CA4
0x180003c97  test    dword ptr [rcx+44h], 100h
0x180003c9e  jnz     loc_180003E25
0x180003ca4  test    rdi, rdi
0x180003ca7  jnz     short loc_180003CC1
0x180003ca9  lea     esi, [rdi+57h]
0x180003cac  cmp     rcx, rbp
0x180003caf  jnz     loc_180003E46
0x180003cb5  mov     eax, esi
0x180003cb7  add     rsp, 58h
0x180003cbb  pop     rdi
0x180003cbc  pop     rsi
0x180003cbd  pop     rbp
0x180003cbe  pop     rbx
0x180003cbf  retn
0x180003cc1  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180003cc4  call    ?SecMgrLockAndCheckAdapterDeleted@@YAKPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrLockAndCheckAdapterDeleted(MSMSEC_INTF_CONTEXT *)
0x180003cc9  mov     esi, eax
0x180003ccb  test    eax, eax
0x180003ccd  jz      short loc_180003D02
0x180003ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x180003cd6  cmp     rcx, rbp
0x180003cd9  jz      short loc_180003CB5
0x180003cdb  test    byte ptr [rcx+44h], 1
0x180003cdf  jz      loc_180003DF2
0x180003ce5  mov     rcx, [rcx+38h]
0x180003ce9  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180003cf0  mov     edx, 26h ; '&'
0x180003cf5  mov     r9d, eax
0x180003cf8  call    WPP_SF_d
0x180003cfd  jmp     loc_180003DEB
0x180003d02  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d09  cmp     rcx, rbp
0x180003d0c  jz      short loc_180003D6F
0x180003d0e  test    byte ptr [rcx+44h], 2
0x180003d12  jz      short loc_180003D6F
0x180003d14  movzx   r9d, byte ptr [rdi+93Bh]
0x180003d1c  mov     edx, 27h ; '''
0x180003d21  movzx   eax, byte ptr [rdi+93Dh]
0x180003d28  movzx   r8d, byte ptr [rdi+93Ch]
0x180003d30  movzx   r10d, byte ptr [rdi+93Ah]
0x180003d38  movzx   r11d, byte ptr [rdi+939h]
0x180003d40  movzx   ebx, byte ptr [rdi+938h]
0x180003d47  mov     rcx, [rcx+38h]
0x180003d4b  mov     [rsp+78h+var_30], eax
0x180003d4f  mov     [rsp+78h+var_38], r8d
0x180003d54  mov     [rsp+78h+var_40], r9d
0x180003d59  mov     r9, rdi
0x180003d5c  mov     [rsp+78h+var_48], r10d
0x180003d61  mov     [rsp+78h+var_50], r11d
0x180003d66  mov     [rsp+78h+var_58], ebx
0x180003d6a  call    WPP_SF_qDDDDDD
0x180003d6f  lea     rcx, [rdi+0B60h]; struct MSMSEC_PREAUTH_CONTEXT *
0x180003d76  call    ?PreAuthPreDestroyAdapter@@YAKPEAUMSMSEC_PREAUTH_CONTEXT@@@Z; PreAuthPreDestroyAdapter(MSMSEC_PREAUTH_CONTEXT *)
0x180003d7b  mov     ecx, [rdi+9C0h]; unsigned int
0x180003d81  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180003d88  mov     dword ptr [rdi+0A38h], 1
0x180003d92  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180003d97  lea     rdx, [rdi+9D0h]
0x180003d9e  mov     r9d, 24Ah
0x180003da4  lea     r8, aSecmgrmarkdele; "SecMgrMarkDeletedAndDerefAdapter"
0x180003dab  mov     rcx, rdi
0x180003dae  call    cs:__imp_ReleaseWriteLock
0x180003db5  nop     dword ptr [rax+rax+00h]
0x180003dba  cmp     dword ptr [rdi+10h], 1
0x180003dbe  jg      loc_180003E63
0x180003dc4  mov     ecx, [rdi+9C0h]; unsigned int
0x180003dca  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180003dd1  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180003dd6  mov     r8d, 25Ah; int
0x180003ddc  lea     rdx, aSecmgrmarkdele; "SecMgrMarkDeletedAndDerefAdapter"
0x180003de3  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180003de6  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180003deb  mov     rcx, cs:WPP_GLOBAL_Control
0x180003df2  cmp     rcx, rbp
0x180003df5  jz      loc_180003CB5
0x180003dfb  test    dword ptr [rcx+44h], 100h
0x180003e02  jz      loc_180003CB5
0x180003e08  mov     rcx, [rcx+38h]
0x180003e0c  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180003e13  mov     edx, 28h ; '('
0x180003e18  mov     r9d, esi
0x180003e1b  call    WPP_SF_d
0x180003e20  jmp     loc_180003CB5
0x180003e25  mov     rcx, [rcx+38h]
0x180003e29  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180003e30  mov     edx, 24h ; '$'
0x180003e35  call    WPP_SF_
0x180003e3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e41  jmp     loc_180003CA4
0x180003e46  test    byte ptr [rcx+44h], 1
0x180003e4a  jz      short loc_180003DF2
0x180003e4c  mov     rcx, [rcx+38h]
0x180003e50  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180003e57  mov     edx, 25h ; '%'
0x180003e5c  call    WPP_SF_
0x180003e61  jmp     short loc_180003DEB
0x180003e63  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180003e68  call    cs:__imp_Sleep
0x180003e6f  nop     dword ptr [rax+rax+00h]
0x180003e74  jmp     loc_180003DBA
```
