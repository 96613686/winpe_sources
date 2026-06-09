# CAANapEnforcementClientCallback::RemoveConnection(CAANapConnection *)

- ea: `0x180003b60`
- end: `0x180003c65`
- name: `?RemoveConnection@CAANapEnforcementClientCallback@@QEAAJPEAVCAANapConnection@@@Z`
- size: `261`
- prototype: `__int64 __fastcall(CAANapEnforcementClientCallback *__hidden this, struct CAANapConnection *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000403c`

## callees

- `0x180003b60`
- `0x1800044e4`
- `0x1800054b8`
- `0x18000c010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180003c4f`
- `KERNEL32!LeaveCriticalSection` at `0x180003c4f`
- `KERNEL32!EnterCriticalSection` at `0x180003b9a`
- `KERNEL32!EnterCriticalSection` at `0x180003b9a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAANapEnforcementClientCallback::RemoveConnection(
        CAANapEnforcementClientCallback *this,
        struct CAANapConnection *a2)
{
  struct CAANapEnforcementClientCallback *v3; // rbp
  char *v4; // rbx
  unsigned int v5; // esi
  __int64 *v6; // rax
  __int64 *v7; // rcx
  __int64 *v8; // r8
  char v10; // [rsp+58h] [rbp+10h] BYREF

  v3 = g_pNECCallback;
  v4 = (char *)g_pNECCallback + 24;
  if ( *((_DWORD *)g_pNECCallback + 8) && *(_QWORD *)v4 )
    EnterCriticalSection(*(LPCRITICAL_SECTION *)v4);
  if ( a2 )
  {
    v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)g_pNECBinding + 64LL))(g_pNECBinding, *(_QWORD *)a2);
    v6 = (__int64 *)*((_QWORD *)v3 + 5);
    v7 = (__int64 *)v6[1];
    v8 = v6;
    if ( !*((_BYTE *)v7 + 25) )
    {
      do
      {
        if ( v7[4] >= (unsigned __int64)a2 )
        {
          v8 = v7;
          v7 = (__int64 *)*v7;
        }
        else
        {
          v7 = (__int64 *)v7[2];
        }
      }
      while ( !*((_BYTE *)v7 + 25) );
      if ( v8 != v6 && (unsigned __int64)a2 >= v8[4] )
        std::_Tree<std::_Tmap_traits<CAANapConnection *,INapEnforcementClientConnection *,std::less<CAANapConnection *>,std::allocator<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>>,0>>::erase(
          (char *)v3 + 40,
          &v10);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        &WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids,
        L"napConnectionItem");
    }
    v5 = -2147024809;
  }
  if ( *((_DWORD *)v4 + 2) && *(_QWORD *)v4 )
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)v4);
  return v5;
}

```

## disassembly

```asm
0x180003b60  mov     rax, rsp
0x180003b63  mov     [rax+8], rcx
0x180003b67  push    rbp
0x180003b68  push    rsi
0x180003b69  push    rdi
0x180003b6a  sub     rsp, 30h
0x180003b6e  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180003b76  mov     [rax+18h], rbx
0x180003b7a  mov     rdi, rdx
0x180003b7d  mov     rbp, cs:?g_pNECCallback@@3PEAVCAANapEnforcementClientCallback@@EA; CAANapEnforcementClientCallback * g_pNECCallback
0x180003b84  lea     rbx, [rbp+18h]
0x180003b88  mov     [rax+8], rbx
0x180003b8c  cmp     dword ptr [rbx+8], 0
0x180003b90  jz      short loc_180003BA1
0x180003b92  mov     rcx, [rbx]; lpCriticalSection
0x180003b95  test    rcx, rcx
0x180003b98  jz      short loc_180003BA1
0x180003b9a  call    cs:__imp_EnterCriticalSection
0x180003ba0  nop
0x180003ba1  test    rdi, rdi
0x180003ba4  jnz     short loc_180003BE6
0x180003ba6  lea     rax, WPP_GLOBAL_Control
0x180003bad  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bb4  cmp     rcx, rax
0x180003bb7  jz      short loc_180003BDF
0x180003bb9  test    byte ptr [rcx+1Ch], 8
0x180003bbd  jz      short loc_180003BDF
0x180003bbf  cmp     byte ptr [rcx+19h], 2
0x180003bc3  jb      short loc_180003BDF
0x180003bc5  lea     edx, [rdi+1Ah]
0x180003bc8  lea     r9, aNapconnectioni; "napConnectionItem"
0x180003bcf  lea     r8, WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids
0x180003bd6  mov     rcx, [rcx+10h]
0x180003bda  call    WPP_SF_S
0x180003bdf  mov     esi, 80070057h
0x180003be4  jmp     short loc_180003C41
0x180003be6  mov     rcx, cs:?g_pNECBinding@@3PEAUINapEnforcementClientBinding@@EA; INapEnforcementClientBinding * g_pNECBinding
0x180003bed  mov     rax, [rcx]
0x180003bf0  mov     rdx, [rdi]
0x180003bf3  mov     rax, [rax+40h]
0x180003bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bfc  mov     esi, eax
0x180003bfe  mov     rax, [rbp+28h]
0x180003c02  mov     rcx, [rax+8]
0x180003c06  mov     r8, rax
0x180003c09  cmp     byte ptr [rcx+19h], 0
0x180003c0d  jnz     short loc_180003C41
0x180003c0f  cmp     [rcx+20h], rdi
0x180003c13  jnb     short loc_180003C1B
0x180003c15  mov     rcx, [rcx+10h]
0x180003c19  jmp     short loc_180003C21
0x180003c1b  mov     r8, rcx
0x180003c1e  mov     rcx, [rcx]
0x180003c21  cmp     byte ptr [rcx+19h], 0
0x180003c25  jz      short loc_180003C0F
0x180003c27  cmp     r8, rax
0x180003c2a  jz      short loc_180003C41
0x180003c2c  cmp     rdi, [r8+20h]
0x180003c30  jb      short loc_180003C41
0x180003c32  lea     rdx, [rsp+48h+arg_8]
0x180003c37  lea     rcx, [rbp+28h]
0x180003c3b  call    ?erase@?$_Tree@V?$_Tmap_traits@PEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@U?$less@PEAVCAANapConnection@@@std@@V?$allocator@U?$pair@QEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<CAANapConnection *,INapEnforcementClientConnection *,std::less<CAANapConnection *>,std::allocator<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>>>>)
0x180003c40  nop
0x180003c41  cmp     dword ptr [rbx+8], 0
0x180003c45  jz      short loc_180003C56
0x180003c47  mov     rcx, [rbx]; lpCriticalSection
0x180003c4a  test    rcx, rcx
0x180003c4d  jz      short loc_180003C56
0x180003c4f  call    cs:__imp_LeaveCriticalSection
0x180003c55  nop
0x180003c56  mov     eax, esi
0x180003c58  mov     rbx, [rsp+48h+arg_10]
0x180003c5d  add     rsp, 30h
0x180003c61  pop     rdi
0x180003c62  pop     rsi
0x180003c63  pop     rbp
0x180003c64  retn
```
