# SampCreateNewHandle(_SAMP_CLIENT_INFO *,void *,_SAMP_CLIENT_INFO * *)

- ea: `0x1800b2460`
- end: `0x1800b255a`
- name: `?SampCreateNewHandle@@YAJPEAU_SAMP_CLIENT_INFO@@PEAXPEAPEAU1@@Z`
- size: `250`
- prototype: `__int64 __fastcall(struct _SAMP_CLIENT_INFO *, void *, struct _SAMP_CLIENT_INFO **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800b2e34`
- `0x1800b34b8`

## callees

- `0x180037284`
- `0x1800b2460`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800b250d`
- `ntdll!RtlCopySid` at `0x1800b250d`
- `ntdll!RtlLengthSid` at `0x1800b24e7`
- `ntdll!RtlLengthSid` at `0x1800b24e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2482`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b24f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2482`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b24f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2525`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2525`

## pseudocode

```c
__int64 __fastcall SampCreateNewHandle(struct _SAMP_CLIENT_INFO *a1, void *a2, struct _SAMP_CLIENT_INFO **a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  PUNICODE_STRING v8; // rcx
  __int64 v9; // rdx
  void *v10; // rcx
  ULONG v11; // esi
  HLOCAL v12; // rax

  *a3 = 0;
  v6 = LocalAlloc(0x40u, 0x18u);
  v7 = v6;
  if ( v6 )
  {
    v10 = 0;
    *(_OWORD *)v6 = 0;
    v6[2] = 0;
    if ( a1 )
    {
      v6[1] = *((_QWORD *)a1 + 1);
      if ( *((_QWORD *)a1 + 2) )
        v10 = (void *)*((_QWORD *)a1 + 2);
    }
    if ( a2 || (a2 = v10) != 0 )
    {
      v11 = RtlLengthSid(a2);
      v12 = LocalAlloc(0x40u, v11);
      v7[2] = v12;
      if ( !v12 )
      {
        LocalFree(v7);
        v8 = WPP_GLOBAL_Control;
        if ( (BYTE4(WPP_GLOBAL_Control[1].Buffer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control[1].Buffer) < 2u )
          return 3221225495LL;
        v9 = 45;
        goto LABEL_16;
      }
      RtlCopySid(v11, v12, a2);
    }
    *a3 = (struct _SAMP_CLIENT_INFO *)v7;
    return 0;
  }
  v8 = WPP_GLOBAL_Control;
  if ( (BYTE4(WPP_GLOBAL_Control[1].Buffer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control[1].Buffer) < 2u )
    return 3221225495LL;
  v9 = 44;
LABEL_16:
  WPP_SF_(*(_QWORD *)&v8[1].Length, v9, &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids);
  return 3221225495LL;
}

```

## disassembly

```asm
0x1800b2460  push    rbx
0x1800b2462  push    rsi
0x1800b2463  push    rdi
0x1800b2464  push    r14
0x1800b2466  sub     rsp, 28h
0x1800b246a  mov     rdi, rdx
0x1800b246d  mov     qword ptr [r8], 0
0x1800b2474  mov     edx, 18h; uBytes
0x1800b2479  mov     rsi, rcx
0x1800b247c  mov     r14, r8
0x1800b247f  lea     ecx, [rdx+28h]; uFlags
0x1800b2482  call    cs:__imp_LocalAlloc
0x1800b2488  mov     rbx, rax
0x1800b248b  test    rax, rax
0x1800b248e  jnz     short loc_1800B24B3
0x1800b2490  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2497  test    byte ptr [rcx+1Ch], 2
0x1800b249b  jz      loc_1800B2553
0x1800b24a1  cmp     byte ptr [rcx+19h], 2
0x1800b24a5  jb      loc_1800B2553
0x1800b24ab  lea     edx, [rax+2Ch]
0x1800b24ae  jmp     loc_1800B2543
0x1800b24b3  xor     eax, eax
0x1800b24b5  xor     ecx, ecx
0x1800b24b7  xorps   xmm0, xmm0
0x1800b24ba  movups  xmmword ptr [rbx], xmm0
0x1800b24bd  mov     [rbx+10h], rax
0x1800b24c1  test    rsi, rsi
0x1800b24c4  jz      short loc_1800B24D7
0x1800b24c6  mov     rax, [rsi+8]
0x1800b24ca  mov     [rbx+8], rax
0x1800b24ce  cmp     [rsi+10h], rcx
0x1800b24d2  cmovnz  rcx, [rsi+10h]
0x1800b24d7  test    rdi, rdi
0x1800b24da  jnz     short loc_1800B24E4
0x1800b24dc  mov     rdi, rcx
0x1800b24df  test    rcx, rcx
0x1800b24e2  jz      short loc_1800B2513
0x1800b24e4  mov     rcx, rdi; Sid
0x1800b24e7  call    cs:__imp_RtlLengthSid
0x1800b24ed  mov     edx, eax; uBytes
0x1800b24ef  mov     ecx, 40h ; '@'; uFlags
0x1800b24f4  mov     esi, eax
0x1800b24f6  call    cs:__imp_LocalAlloc
0x1800b24fc  mov     [rbx+10h], rax
0x1800b2500  test    rax, rax
0x1800b2503  jz      short loc_1800B2522
0x1800b2505  mov     r8, rdi; SourceSid
0x1800b2508  mov     rdx, rax; DestinationSid
0x1800b250b  mov     ecx, esi; DestinationSidLength
0x1800b250d  call    cs:__imp_RtlCopySid
0x1800b2513  mov     [r14], rbx
0x1800b2516  xor     eax, eax
0x1800b2518  add     rsp, 28h
0x1800b251c  pop     r14
0x1800b251e  pop     rdi
0x1800b251f  pop     rsi
0x1800b2520  pop     rbx
0x1800b2521  retn
0x1800b2522  mov     rcx, rbx; hMem
0x1800b2525  call    cs:__imp_LocalFree
0x1800b252b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2532  test    byte ptr [rcx+1Ch], 2
0x1800b2536  jz      short loc_1800B2553
0x1800b2538  cmp     byte ptr [rcx+19h], 2
0x1800b253c  jb      short loc_1800B2553
0x1800b253e  mov     edx, 2Dh ; '-'
0x1800b2543  mov     rcx, [rcx+10h]
0x1800b2547  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x1800b254e  call    WPP_SF_
0x1800b2553  mov     eax, 0C0000017h
0x1800b2558  jmp     short loc_1800B2518
```
