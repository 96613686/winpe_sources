# FilterSendNetBufferListsCompleteWDI

- ea: `0x14000a880`
- end: `0x14000ab44`
- name: `FilterSendNetBufferListsCompleteWDI`
- size: `708`
- prototype: `__int64 __fastcall(PNET_BUFFER_LIST NetBufferList)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000a850`

## callees

- `0x14000a880`
- `0x14000ada8`
- `0x14000cd98`
- `0x14000eed4`
- `0x14000f150`

## import_xrefs

- `NDIS!NdisFreeNetBufferListContext` at `0x14000a8df`
- `NDIS!NdisFreeNetBufferListContext` at `0x14000a8df`

## pseudocode

```c
void __fastcall FilterSendNetBufferListsCompleteWDI(PNET_BUFFER_LIST NetBufferList, unsigned int a2)
{
  __int64 v2; // r12
  __int64 v3; // rdi
  int v4; // esi
  __int64 *v6; // r15
  PNET_BUFFER_LIST v7; // rbx
  PNET_BUFFER_LIST_CONTEXT Context; // rcx
  struct _NET_BUFFER_LIST *Alignment; // r14
  __int64 v10; // rbp
  int v11; // edx
  __int64 v12; // r8
  __int64 v13; // rbx
  __int64 v14; // r8
  __int64 v15; // [rsp+60h] [rbp+8h] BYREF

  if ( NetBufferList )
  {
    v2 = 0;
    v3 = 0;
    v15 = 0;
    v4 = 0;
    v6 = &v15;
    v7 = NetBufferList;
    while ( 1 )
    {
      Context = v7->Context;
      Alignment = (struct _NET_BUFFER_LIST *)v7->Link.Alignment;
      v7->Link.Alignment = 0;
      v10 = *(_QWORD *)&Context->ContextData[Context->Offset];
      NdisFreeNetBufferListContext(v7, 0x10u);
      if ( !v10
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        WPP_SF_ssL(
          WPP_GLOBAL_Control->AttachedDevice,
          v11,
          v12,
          (unsigned int)"pFilterMpCtx",
          (__int64)"onecoreuap\\net\\vwifi\\filter\\filter.c",
          254);
      }
      if ( v3 != v10 )
      {
        if ( v2 && v3 )
        {
          if ( !*(_BYTE *)(v3 + 2)
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            WPP_SF_ssL(
              WPP_GLOBAL_Control->AttachedDevice,
              v11,
              v12,
              (unsigned int)"pLastFilterMpCtx->fMpStarted",
              (__int64)"onecoreuap\\net\\vwifi\\filter\\filter.c",
              9);
          }
          if ( *(_BYTE *)(v3 + 2) )
          {
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(v3 + 72))(*(_QWORD *)(v3 + 56), v2, a2);
          }
          else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 223, v12, *(unsigned int *)(v3 + 104), v4);
          }
          _InterlockedAdd((volatile signed __int32 *)(v3 + 124), -v4);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 224, v12, *(unsigned int *)(v3 + 104), v4);
          }
        }
        v6 = &v15;
        v4 = 0;
        v3 = v10;
      }
      *v6 = (__int64)v7;
      ++v4;
      v6 = (__int64 *)v7;
      v7 = Alignment;
      if ( !Alignment )
        break;
      v2 = v15;
    }
    v13 = v15;
    if ( v15 && v3 )
    {
      if ( *(_BYTE *)(v3 + 2)
        || (TraceAssert("pLastFilterMpCtx->fMpStarted", "onecoreuap\\net\\vwifi\\filter\\filter.c", 3636),
            *(_BYTE *)(v3 + 2)) )
      {
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(v3 + 72))(*(_QWORD *)(v3 + 56), v13, a2);
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 225, v14, *(unsigned int *)(v3 + 104), v4);
      }
      _InterlockedAdd((volatile signed __int32 *)(v3 + 124), -v4);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 226, v14, *(unsigned int *)(v3 + 104), v4);
    }
  }
}

```

## disassembly

```asm
0x14000a880  test    rcx, rcx
0x14000a883  jz      locret_14000A990
0x14000a889  mov     [rsp+arg_18], rbx
0x14000a88e  push    rsi
0x14000a88f  push    rdi
0x14000a890  push    r12
0x14000a892  push    r13
0x14000a894  push    r15
0x14000a896  sub     rsp, 30h
0x14000a89a  xor     r12d, r12d
0x14000a89d  mov     [rsp+58h+arg_8], rbp
0x14000a8a2  xor     edi, edi
0x14000a8a4  mov     [rsp+58h+arg_0], r12
0x14000a8a9  xor     esi, esi
0x14000a8ab  mov     [rsp+58h+arg_10], r14
0x14000a8b0  mov     r13d, edx
0x14000a8b3  lea     r15, [rsp+58h+arg_0]
0x14000a8b8  mov     rbx, rcx
0x14000a8bb  nop     dword ptr [rax+rax+00h]
0x14000a8c0  mov     rcx, [rbx+10h]
0x14000a8c4  mov     edx, 10h; ContextSize
0x14000a8c9  mov     r14, [rbx]
0x14000a8cc  mov     qword ptr [rbx], 0
0x14000a8d3  movzx   eax, word ptr [rcx+0Ah]
0x14000a8d7  mov     rbp, [rax+rcx+10h]
0x14000a8dc  mov     rcx, rbx; NetBufferList
0x14000a8df  call    cs:__imp_NdisFreeNetBufferListContext
0x14000a8e6  nop     dword ptr [rax+rax+00h]
0x14000a8eb  test    rbp, rbp
0x14000a8ee  jz      loc_14000A992
0x14000a8f4  cmp     rdi, rbp
0x14000a8f7  jz      short loc_14000A90C
0x14000a8f9  test    r12, r12
0x14000a8fc  jnz     loc_14000A9DD
0x14000a902  lea     r15, [rsp+58h+arg_0]
0x14000a907  xor     esi, esi
0x14000a909  mov     rdi, rbp
0x14000a90c  mov     [r15], rbx
0x14000a90f  inc     esi
0x14000a911  mov     r15, rbx
0x14000a914  mov     rbx, r14
0x14000a917  test    r14, r14
0x14000a91a  jz      short loc_14000A923
0x14000a91c  mov     r12, [rsp+58h+arg_0]
0x14000a921  jmp     short loc_14000A8C0
0x14000a923  mov     rbx, [rsp+58h+arg_0]
0x14000a928  mov     r14, [rsp+58h+arg_10]
0x14000a92d  mov     rbp, [rsp+58h+arg_8]
0x14000a932  test    rbx, rbx
0x14000a935  jz      short loc_14000A97F
0x14000a937  test    rdi, rdi
0x14000a93a  jz      short loc_14000A97F
0x14000a93c  cmp     byte ptr [rdi+2], 0
0x14000a940  jz      loc_14000AAC9
0x14000a946  mov     rax, [rdi+48h]
0x14000a94a  mov     r8d, r13d
0x14000a94d  mov     rcx, [rdi+38h]
0x14000a951  mov     rdx, rbx
0x14000a954  call    _guard_dispatch_icall
0x14000a959  mov     eax, esi
0x14000a95b  neg     eax
0x14000a95d  lock add [rdi+7Ch], eax
0x14000a961  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a968  lea     rax, WPP_GLOBAL_Control
0x14000a96f  cmp     rcx, rax
0x14000a972  jz      short loc_14000A97F
0x14000a974  mov     eax, [rcx+2Ch]
0x14000a977  test    al, 4
0x14000a979  jnz     loc_14000AB29
0x14000a97f  mov     rbx, [rsp+58h+arg_18]
0x14000a984  add     rsp, 30h
0x14000a988  pop     r15
0x14000a98a  pop     r13
0x14000a98c  pop     r12
0x14000a98e  pop     rdi
0x14000a98f  pop     rsi
0x14000a990  retn
0x14000a992  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a999  lea     rax, WPP_GLOBAL_Control
0x14000a9a0  cmp     rcx, rax
0x14000a9a3  jz      loc_14000A8F4
0x14000a9a9  mov     eax, [rcx+2Ch]
0x14000a9ac  test    al, 2
0x14000a9ae  jz      loc_14000A8F4
0x14000a9b4  mov     rcx, [rcx+18h]
0x14000a9b8  lea     rax, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000a9bf  mov     [rsp+58h+var_30], 0DFEh
0x14000a9c7  lea     r9, aPfiltermpctx; "pFilterMpCtx"
0x14000a9ce  mov     [rsp+58h+var_38], rax
0x14000a9d3  call    WPP_SF_ssL
0x14000a9d8  jmp     loc_14000A8F4
0x14000a9dd  test    rdi, rdi
0x14000a9e0  jz      loc_14000A902
0x14000a9e6  cmp     byte ptr [rdi+2], 0
0x14000a9ea  jnz     loc_14000AABD
0x14000a9f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a9f7  lea     r15, WPP_GLOBAL_Control
0x14000a9fe  cmp     rcx, r15
0x14000aa01  jnz     loc_14000AA89
0x14000aa07  cmp     byte ptr [rdi+2], 0
0x14000aa0b  jz      short loc_14000AA5E
0x14000aa0d  mov     rax, [rdi+48h]
0x14000aa11  mov     r8d, r13d
0x14000aa14  mov     rcx, [rdi+38h]
0x14000aa18  mov     rdx, r12
0x14000aa1b  call    _guard_dispatch_icall
0x14000aa20  mov     eax, esi
0x14000aa22  neg     eax
0x14000aa24  lock add [rdi+7Ch], eax
0x14000aa28  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aa2f  cmp     rcx, r15
0x14000aa32  jz      loc_14000A902
0x14000aa38  mov     eax, [rcx+2Ch]
0x14000aa3b  test    al, 4
0x14000aa3d  jz      loc_14000A902
0x14000aa43  mov     r9d, [rdi+68h]
0x14000aa47  mov     edx, 0E0h
0x14000aa4c  mov     rcx, [rcx+18h]
0x14000aa50  mov     dword ptr [rsp+58h+var_38], esi
0x14000aa54  call    WPP_SF_Dd
0x14000aa59  jmp     loc_14000A902
0x14000aa5e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aa65  cmp     rcx, r15
0x14000aa68  jz      short loc_14000AA20
0x14000aa6a  mov     eax, [rcx+2Ch]
0x14000aa6d  test    al, 1
0x14000aa6f  jz      short loc_14000AA20
0x14000aa71  mov     r9d, [rdi+68h]
0x14000aa75  mov     edx, 0DFh
0x14000aa7a  mov     rcx, [rcx+18h]
0x14000aa7e  mov     dword ptr [rsp+58h+var_38], esi
0x14000aa82  call    WPP_SF_Dd
0x14000aa87  jmp     short loc_14000AA20
0x14000aa89  mov     eax, [rcx+2Ch]
0x14000aa8c  test    al, 2
0x14000aa8e  jz      loc_14000AA07
0x14000aa94  mov     rcx, [rcx+18h]
0x14000aa98  lea     rax, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000aa9f  mov     [rsp+58h+var_30], 0E09h
0x14000aaa7  lea     r9, aPlastfiltermpc; "pLastFilterMpCtx->fMpStarted"
0x14000aaae  mov     [rsp+58h+var_38], rax
0x14000aab3  call    WPP_SF_ssL
0x14000aab8  jmp     loc_14000AA07
0x14000aabd  lea     r15, WPP_GLOBAL_Control
0x14000aac4  jmp     loc_14000AA07
0x14000aac9  mov     r8d, 0E34h
0x14000aacf  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000aad6  lea     rcx, aPlastfiltermpc; "pLastFilterMpCtx->fMpStarted"
0x14000aadd  call    TraceAssert
0x14000aae2  cmp     byte ptr [rdi+2], 0
0x14000aae6  jnz     loc_14000A946
0x14000aaec  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aaf3  lea     rax, WPP_GLOBAL_Control
0x14000aafa  cmp     rcx, rax
0x14000aafd  jz      loc_14000A959
0x14000ab03  mov     eax, [rcx+2Ch]
0x14000ab06  test    al, 1
0x14000ab08  jz      loc_14000A959
0x14000ab0e  mov     r9d, [rdi+68h]
0x14000ab12  mov     edx, 0E1h
0x14000ab17  mov     rcx, [rcx+18h]
0x14000ab1b  mov     dword ptr [rsp+58h+var_38], esi
0x14000ab1f  call    WPP_SF_Dd
0x14000ab24  jmp     loc_14000A959
0x14000ab29  mov     r9d, [rdi+68h]
0x14000ab2d  mov     edx, 0E2h
0x14000ab32  mov     rcx, [rcx+18h]
0x14000ab36  mov     dword ptr [rsp+58h+var_38], esi
0x14000ab3a  call    WPP_SF_Dd
0x14000ab3f  jmp     loc_14000A97F
```
