# CredHandlerRelease

- ea: `0x180008664`
- end: `0x1800087ec`
- name: `CredHandlerRelease`
- size: `392`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `6`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001bb0`
- `0x180019aa0`
- `0x180019bd0`
- `0x180019f80`
- `0x18001e4b0`
- `0x1800206d0`

## callees

- `0x1800085dc`
- `0x180008664`
- `0x180011fec`
- `0x1800185b8`
- `0x1800192a8`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180008722`
- `ntdll!RtlLeaveCriticalSection` at `0x18000877c`
- `ntdll!RtlLeaveCriticalSection` at `0x180008722`
- `ntdll!RtlLeaveCriticalSection` at `0x18000877c`
- `ntdll!RtlEnterCriticalSection` at `0x1800086ef`
- `ntdll!RtlEnterCriticalSection` at `0x1800086ef`

## pseudocode

```c
__int64 __fastcall CredHandlerRelease(volatile signed __int32 *hMem)
{
  unsigned int v2; // esi
  int v3; // edi
  PVOID *v4; // rcx
  _QWORD *v5; // rax
  HLOCAL *v6; // rcx

  v2 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Du, &WPP_04f0a9bd24f73eb2158b77697939d7e6_Traceguids, hMem);
  v3 = _InterlockedDecrement(hMem + 4);
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Eu, &WPP_04f0a9bd24f73eb2158b77697939d7e6_Traceguids, v3);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v3 )
  {
    RtlEnterCriticalSection(&l_CredentialCritSect);
    if ( *((_DWORD *)hMem + 4) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Fu, &WPP_04f0a9bd24f73eb2158b77697939d7e6_Traceguids);
      RtlLeaveCriticalSection(&l_CredentialCritSect);
    }
    else
    {
      if ( !*((_DWORD *)hMem + 5) )
      {
        v5 = *(_QWORD **)hMem;
        if ( *(volatile signed __int32 **)(*(_QWORD *)hMem + 8LL) != hMem
          || (v6 = (HLOCAL *)*((_QWORD *)hMem + 1), *v6 != hMem) )
        {
          __fastfail(3u);
        }
        *v6 = v5;
        v5[1] = v6;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x20u, &WPP_04f0a9bd24f73eb2158b77697939d7e6_Traceguids, hMem);
      }
      RtlLeaveCriticalSection(&l_CredentialCritSect);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x21u, &WPP_04f0a9bd24f73eb2158b77697939d7e6_Traceguids, hMem);
      v2 = CredentialFree((HLOCAL)hMem);
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && *((char *)v4 + 28) < 0 )
    WPP_SF_d((TRACEHANDLE)v4[2], 0x22u, &WPP_04f0a9bd24f73eb2158b77697939d7e6_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x180008664  push    rbx
0x180008666  push    rbp
0x180008667  push    rsi
0x180008668  push    rdi
0x180008669  push    r14
0x18000866b  sub     rsp, 20h
0x18000866f  mov     rbx, rcx
0x180008672  xor     esi, esi
0x180008674  mov     rcx, cs:WPP_GLOBAL_Control
0x18000867b  lea     rbp, WPP_GLOBAL_Control
0x180008682  lea     r14, WPP_04f0a9bd24f73eb2158b77697939d7e6_Traceguids
0x180008689  cmp     rcx, rbp
0x18000868c  jz      short loc_1800086A6
0x18000868e  test    byte ptr [rcx+1Ch], 80h
0x180008692  jz      short loc_1800086A6
0x180008694  mov     rcx, [rcx+10h]
0x180008698  lea     edx, [rsi+1Dh]
0x18000869b  mov     r9, rbx
0x18000869e  mov     r8, r14
0x1800086a1  call    WPP_SF_q
0x1800086a6  or      edi, 0FFFFFFFFh
0x1800086a9  lock xadd [rbx+10h], edi
0x1800086ae  dec     edi
0x1800086b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086b7  cmp     rcx, rbp
0x1800086ba  jz      short loc_1800086DD
0x1800086bc  test    byte ptr [rcx+1Ch], 4
0x1800086c0  jz      short loc_1800086DD
0x1800086c2  mov     rcx, [rcx+10h]
0x1800086c6  mov     edx, 1Eh
0x1800086cb  mov     r9d, edi
0x1800086ce  mov     r8, r14
0x1800086d1  call    WPP_SF_d
0x1800086d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086dd  test    edi, edi
0x1800086df  jnz     loc_1800087B9
0x1800086e5  lea     rdi, ?l_CredentialCritSect@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION l_CredentialCritSect
0x1800086ec  mov     rcx, rdi; CriticalSection
0x1800086ef  call    cs:__imp_RtlEnterCriticalSection
0x1800086f5  mov     eax, [rbx+10h]
0x1800086f8  test    eax, eax
0x1800086fa  jz      short loc_18000872D
0x1800086fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180008703  cmp     rcx, rbp
0x180008706  jz      short loc_18000871F
0x180008708  test    byte ptr [rcx+1Ch], 4
0x18000870c  jz      short loc_18000871F
0x18000870e  mov     rcx, [rcx+10h]
0x180008712  mov     edx, 1Fh
0x180008717  mov     r8, r14
0x18000871a  call    WPP_SF_
0x18000871f  mov     rcx, rdi; CriticalSection
0x180008722  call    cs:__imp_RtlLeaveCriticalSection
0x180008728  jmp     loc_1800087B2
0x18000872d  cmp     [rbx+14h], esi
0x180008730  jnz     short loc_180008779
0x180008732  mov     rax, [rbx]
0x180008735  cmp     [rax+8], rbx
0x180008739  jnz     loc_1800087E5
0x18000873f  mov     rcx, [rbx+8]
0x180008743  cmp     [rcx], rbx
0x180008746  jnz     loc_1800087E5
0x18000874c  mov     [rcx], rax
0x18000874f  mov     [rax+8], rcx
0x180008753  mov     rcx, cs:WPP_GLOBAL_Control
0x18000875a  cmp     rcx, rbp
0x18000875d  jz      short loc_180008779
0x18000875f  test    byte ptr [rcx+1Ch], 4
0x180008763  jz      short loc_180008779
0x180008765  mov     rcx, [rcx+10h]
0x180008769  mov     edx, 20h ; ' '
0x18000876e  mov     r9, rbx
0x180008771  mov     r8, r14
0x180008774  call    WPP_SF_q
0x180008779  mov     rcx, rdi; CriticalSection
0x18000877c  call    cs:__imp_RtlLeaveCriticalSection
0x180008782  mov     rcx, cs:WPP_GLOBAL_Control
0x180008789  cmp     rcx, rbp
0x18000878c  jz      short loc_1800087A8
0x18000878e  test    byte ptr [rcx+1Ch], 4
0x180008792  jz      short loc_1800087A8
0x180008794  mov     rcx, [rcx+10h]
0x180008798  mov     edx, 21h ; '!'
0x18000879d  mov     r9, rbx
0x1800087a0  mov     r8, r14
0x1800087a3  call    WPP_SF_q
0x1800087a8  mov     rcx, rbx; hMem
0x1800087ab  call    CredentialFree
0x1800087b0  mov     esi, eax
0x1800087b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087b9  cmp     rcx, rbp
0x1800087bc  jz      short loc_1800087D8
0x1800087be  test    byte ptr [rcx+1Ch], 80h
0x1800087c2  jz      short loc_1800087D8
0x1800087c4  mov     rcx, [rcx+10h]
0x1800087c8  mov     edx, 22h ; '"'
0x1800087cd  mov     r9d, esi
0x1800087d0  mov     r8, r14
0x1800087d3  call    WPP_SF_d
0x1800087d8  mov     eax, esi
0x1800087da  add     rsp, 20h
0x1800087de  pop     r14
0x1800087e0  pop     rdi
0x1800087e1  pop     rsi
0x1800087e2  pop     rbp
0x1800087e3  pop     rbx
0x1800087e4  retn
0x1800087e5  mov     ecx, 3
0x1800087ea  int     29h; Win8: RtlFailFast(ecx)
```
