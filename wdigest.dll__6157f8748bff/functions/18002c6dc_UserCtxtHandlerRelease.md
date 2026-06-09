# UserCtxtHandlerRelease

- ea: `0x18002c6dc`
- end: `0x18002c822`
- name: `UserCtxtHandlerRelease`
- size: `326`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `8`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180030d40`
- `0x180030ee0`
- `0x180031080`
- `0x1800316a0`
- `0x180031910`
- `0x180032060`
- `0x1800322b0`
- `0x180032670`

## callees

- `0x180011fec`
- `0x1800185b8`
- `0x1800192a8`
- `0x18001a394`
- `0x18002c364`
- `0x18002c6dc`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002c7e4`
- `ntdll!RtlLeaveCriticalSection` at `0x18002c7e4`
- `ntdll!RtlEnterCriticalSection` at `0x18002c720`
- `ntdll!RtlEnterCriticalSection` at `0x18002c720`

## pseudocode

```c
__int64 __fastcall UserCtxtHandlerRelease(_DWORD *hMem)
{
  unsigned int v2; // edi
  _QWORD *v3; // rax
  HLOCAL *v4; // rcx
  int v5; // eax

  v2 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x17u, &WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids);
  RtlEnterCriticalSection(&l_UserCtxtCritSect);
  --hMem[10];
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0x18u,
      &WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids,
      *((_QWORD *)hMem + 3),
      hMem[10]);
  if ( !*((_QWORD *)hMem + 5) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x19u, &WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids, hMem);
    v3 = *(_QWORD **)hMem;
    if ( *(_DWORD **)(*(_QWORD *)hMem + 8LL) != hMem || (v4 = (HLOCAL *)*((_QWORD *)hMem + 1), *v4 != hMem) )
      __fastfail(3u);
    *v4 = v3;
    v3[1] = v4;
    v5 = UserCtxtFree(hMem);
    v2 = v5;
    if ( v5 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Au, &WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids, v5);
  }
  RtlLeaveCriticalSection(&l_UserCtxtCritSect);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Bu, &WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x18002c6dc  push    rbx
0x18002c6de  push    rbp
0x18002c6df  push    rsi
0x18002c6e0  push    rdi
0x18002c6e1  sub     rsp, 38h
0x18002c6e5  mov     rbx, rcx
0x18002c6e8  xor     edi, edi
0x18002c6ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c6f1  lea     rsi, WPP_GLOBAL_Control
0x18002c6f8  lea     rbp, WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids
0x18002c6ff  cmp     rcx, rsi
0x18002c702  jz      short loc_18002C719
0x18002c704  test    byte ptr [rcx+1Ch], 80h
0x18002c708  jz      short loc_18002C719
0x18002c70a  mov     rcx, [rcx+10h]
0x18002c70e  lea     edx, [rdi+17h]
0x18002c711  mov     r8, rbp
0x18002c714  call    WPP_SF_
0x18002c719  lea     rcx, ?l_UserCtxtCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002c720  call    cs:__imp_RtlEnterCriticalSection
0x18002c726  mov     eax, [rbx+28h]
0x18002c729  dec     eax
0x18002c72b  mov     [rbx+28h], eax
0x18002c72e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c735  cmp     rcx, rsi
0x18002c738  jz      short loc_18002C75C
0x18002c73a  test    byte ptr [rcx+1Ch], 4
0x18002c73e  jz      short loc_18002C75C
0x18002c740  mov     eax, [rbx+28h]
0x18002c743  mov     edx, 18h
0x18002c748  mov     r9, [rbx+18h]
0x18002c74c  mov     r8, rbp
0x18002c74f  mov     rcx, [rcx+10h]
0x18002c753  mov     [rsp+58h+var_38], eax
0x18002c757  call    WPP_SF_qD
0x18002c75c  mov     eax, [rbx+28h]
0x18002c75f  test    eax, eax
0x18002c761  jnz     short loc_18002C7DD
0x18002c763  cmp     [rbx+2Ch], edi
0x18002c766  jnz     short loc_18002C7DD
0x18002c768  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c76f  cmp     rcx, rsi
0x18002c772  jz      short loc_18002C78C
0x18002c774  test    byte ptr [rcx+1Ch], 4
0x18002c778  jz      short loc_18002C78C
0x18002c77a  mov     rcx, [rcx+10h]
0x18002c77e  lea     edx, [rax+19h]
0x18002c781  mov     r9, rbx
0x18002c784  mov     r8, rbp
0x18002c787  call    WPP_SF_q
0x18002c78c  mov     rax, [rbx]
0x18002c78f  cmp     [rax+8], rbx
0x18002c793  jnz     loc_18002C81B
0x18002c799  mov     rcx, [rbx+8]
0x18002c79d  cmp     [rcx], rbx
0x18002c7a0  jnz     short loc_18002C81B
0x18002c7a2  mov     [rcx], rax
0x18002c7a5  mov     [rax+8], rcx
0x18002c7a9  mov     rcx, rbx; hMem
0x18002c7ac  call    UserCtxtFree
0x18002c7b1  mov     edi, eax
0x18002c7b3  test    eax, eax
0x18002c7b5  jns     short loc_18002C7DD
0x18002c7b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c7be  cmp     rcx, rsi
0x18002c7c1  jz      short loc_18002C7DD
0x18002c7c3  test    byte ptr [rcx+1Ch], 1
0x18002c7c7  jz      short loc_18002C7DD
0x18002c7c9  mov     rcx, [rcx+10h]
0x18002c7cd  mov     edx, 1Ah
0x18002c7d2  mov     r9d, eax
0x18002c7d5  mov     r8, rbp
0x18002c7d8  call    WPP_SF_d
0x18002c7dd  lea     rcx, ?l_UserCtxtCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002c7e4  call    cs:__imp_RtlLeaveCriticalSection
0x18002c7ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c7f1  cmp     rcx, rsi
0x18002c7f4  jz      short loc_18002C810
0x18002c7f6  test    byte ptr [rcx+1Ch], 80h
0x18002c7fa  jz      short loc_18002C810
0x18002c7fc  mov     rcx, [rcx+10h]
0x18002c800  mov     edx, 1Bh
0x18002c805  mov     r9d, edi
0x18002c808  mov     r8, rbp
0x18002c80b  call    WPP_SF_d
0x18002c810  mov     eax, edi
0x18002c812  add     rsp, 38h
0x18002c816  pop     rdi
0x18002c817  pop     rsi
0x18002c818  pop     rbp
0x18002c819  pop     rbx
0x18002c81a  retn
0x18002c81b  mov     ecx, 3
0x18002c820  int     29h; Win8: RtlFailFast(ecx)
```
