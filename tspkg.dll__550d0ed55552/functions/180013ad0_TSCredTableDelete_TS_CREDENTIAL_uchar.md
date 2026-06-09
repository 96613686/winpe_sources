# TSCredTableDelete(_TS_CREDENTIAL *,uchar)

- ea: `0x180013ad0`
- end: `0x180013c5d`
- name: `?TSCredTableDelete@@YAXPEAU_TS_CREDENTIAL@@E@Z`
- size: `397`
- prototype: `void __fastcall(struct _TS_CREDENTIAL *, unsigned __int8)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800052f0`
- `0x180013120`

## callees

- `0x1800053d0`
- `0x180013ad0`
- `0x180016650`
- `0x1800166e8`
- `0x180016738`
- `0x18001679c`
- `0x18001d010`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180013bdb`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180013bdb`
- `ntdll!RtlAcquireResourceExclusive` at `0x180013b2b`
- `ntdll!RtlAcquireResourceExclusive` at `0x180013b2b`
- `ntdll!RtlReleaseResource` at `0x180013c4e`
- `ntdll!RtlReleaseResource` at `0x180013c4e`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180013b3d`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180013b3d`

## pseudocode

```c
void __fastcall TSCredTableDelete(struct _TS_CREDENTIAL *a1, char a2)
{
  int v3; // edi
  __int64 v4; // rdx
  PVOID v5; // rbp
  __int64 v6; // r8
  unsigned int v7; // edi
  int v8; // eax
  __int128 Buffer; // [rsp+40h] [rbp-58h] BYREF
  __int128 v10; // [rsp+50h] [rbp-48h] BYREF
  __int64 v11; // [rsp+60h] [rbp-38h]

  v11 = 0;
  Buffer = 0;
  v10 = 0;
  if ( a2 || ((unsigned __int8 (__fastcall *)(__int128 *))TSGlobalLsaFunctions->GetCallInfo)(&v10) )
  {
    v3 = 1;
    *(_QWORD *)&Buffer = a1;
    RtlAcquireResourceExclusive(&TSGlobalCredTableLock, 1u);
    v5 = RtlLookupElementGenericTableAvl(&TSGlobalCredTable, &Buffer);
    if ( v5 )
    {
      if ( HIDWORD(v10) )
        v3 = HIDWORD(v10);
      v7 = -v3;
      if ( HIDWORD(v10)
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_qddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v6, a1, *((_DWORD *)v5 + 2), HIDWORD(v10), v7);
      }
      _InterlockedAdd((volatile signed __int32 *)v5 + 2, v7);
      v8 = *((_DWORD *)v5 + 2);
      if ( v8 > 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_qdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v6, a1, HIDWORD(v10), v8);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids,
            a1,
            HIDWORD(v10));
        if ( RtlDeleteElementGenericTableAvl(&TSGlobalCredTable, &Buffer) )
          TSDereferenceCredential((struct _TS_CREDENTIAL *)Buffer);
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids, a1);
    }
    RtlReleaseResource(&TSGlobalCredTableLock);
  }
}

```

## disassembly

```asm
0x180013ad0  push    rbx
0x180013ad2  push    rbp
0x180013ad3  push    rsi
0x180013ad4  push    rdi
0x180013ad5  sub     rsp, 78h
0x180013ad9  xor     eax, eax
0x180013adb  xorps   xmm0, xmm0
0x180013ade  mov     [rsp+98h+var_38], rax
0x180013ae3  xorps   xmm1, xmm1
0x180013ae6  mov     rsi, rcx
0x180013ae9  movups  [rsp+98h+Buffer], xmm0
0x180013aee  movups  [rsp+98h+var_48], xmm1
0x180013af3  test    dl, dl
0x180013af5  jnz     short loc_180013B17
0x180013af7  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180013afe  lea     rcx, [rsp+98h+var_48]
0x180013b03  mov     rax, [rax+0C0h]
0x180013b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b0f  test    al, al
0x180013b11  jz      loc_180013C54
0x180013b17  mov     edi, 1
0x180013b1c  mov     qword ptr [rsp+98h+Buffer], rsi
0x180013b21  mov     dl, dil; Wait
0x180013b24  lea     rcx, ?TSGlobalCredTableLock@@3U_RTL_RESOURCE@@A; Resource
0x180013b2b  call    cs:__imp_RtlAcquireResourceExclusive
0x180013b31  lea     rdx, [rsp+98h+Buffer]; Buffer
0x180013b36  lea     rcx, ?TSGlobalCredTable@@3U_RTL_AVL_TABLE@@A; Table
0x180013b3d  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180013b43  lea     rbx, WPP_GLOBAL_Control
0x180013b4a  mov     rbp, rax
0x180013b4d  test    rax, rax
0x180013b50  jz      loc_180013C1D
0x180013b56  mov     eax, dword ptr [rsp+98h+var_48+0Ch]
0x180013b5a  test    eax, eax
0x180013b5c  cmovnz  edi, eax
0x180013b5f  neg     edi
0x180013b61  test    eax, eax
0x180013b63  jz      short loc_180013B92
0x180013b65  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b6c  cmp     rcx, rbx
0x180013b6f  jz      short loc_180013B92
0x180013b71  test    byte ptr [rcx+1Ch], 8
0x180013b75  jz      short loc_180013B92
0x180013b77  mov     rcx, [rcx+10h]
0x180013b7b  mov     r9, rsi
0x180013b7e  mov     [rsp+98h+var_68], edi
0x180013b82  mov     [rsp+98h+var_70], eax
0x180013b86  mov     eax, [rbp+8]
0x180013b89  mov     [rsp+98h+var_78], eax
0x180013b8d  call    WPP_SF_qddd
0x180013b92  lock add [rbp+8], edi
0x180013b96  mov     eax, [rbp+8]
0x180013b99  test    eax, eax
0x180013b9b  jg      short loc_180013BF1
0x180013b9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ba4  cmp     rcx, rbx
0x180013ba7  jz      short loc_180013BCF
0x180013ba9  test    byte ptr [rcx+1Ch], 8
0x180013bad  jz      short loc_180013BCF
0x180013baf  mov     eax, dword ptr [rsp+98h+var_48+0Ch]
0x180013bb3  lea     r8, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids
0x180013bba  mov     rcx, [rcx+10h]
0x180013bbe  mov     edx, 0Fh
0x180013bc3  mov     r9, rsi
0x180013bc6  mov     [rsp+98h+var_78], eax
0x180013bca  call    WPP_SF_qd
0x180013bcf  lea     rdx, [rsp+98h+Buffer]; Buffer
0x180013bd4  lea     rcx, ?TSGlobalCredTable@@3U_RTL_AVL_TABLE@@A; Table
0x180013bdb  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180013be1  test    al, al
0x180013be3  jz      short loc_180013C47
0x180013be5  mov     rcx, qword ptr [rsp+98h+Buffer]; struct _TS_CREDENTIAL *
0x180013bea  call    ?TSDereferenceCredential@@YAXPEAU_TS_CREDENTIAL@@@Z; TSDereferenceCredential(_TS_CREDENTIAL *)
0x180013bef  jmp     short loc_180013C47
0x180013bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180013bf8  cmp     rcx, rbx
0x180013bfb  jz      short loc_180013C47
0x180013bfd  test    byte ptr [rcx+1Ch], 8
0x180013c01  jz      short loc_180013C47
0x180013c03  mov     rcx, [rcx+10h]
0x180013c07  mov     r9, rsi
0x180013c0a  mov     [rsp+98h+var_70], eax
0x180013c0e  mov     eax, dword ptr [rsp+98h+var_48+0Ch]
0x180013c12  mov     [rsp+98h+var_78], eax
0x180013c16  call    WPP_SF_qdd
0x180013c1b  jmp     short loc_180013C47
0x180013c1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c24  cmp     rcx, rbx
0x180013c27  jz      short loc_180013C47
0x180013c29  test    byte ptr [rcx+1Ch], 8
0x180013c2d  jz      short loc_180013C47
0x180013c2f  mov     rcx, [rcx+10h]
0x180013c33  lea     r8, WPP_bf7026bbac8b39131028b28c131bfccd_Traceguids
0x180013c3a  mov     edx, 11h
0x180013c3f  mov     r9, rsi
0x180013c42  call    WPP_SF_q
0x180013c47  lea     rcx, ?TSGlobalCredTableLock@@3U_RTL_RESOURCE@@A; Resource
0x180013c4e  call    cs:__imp_RtlReleaseResource
0x180013c54  add     rsp, 78h
0x180013c58  pop     rdi
0x180013c59  pop     rsi
0x180013c5a  pop     rbp
0x180013c5b  pop     rbx
0x180013c5c  retn
```
