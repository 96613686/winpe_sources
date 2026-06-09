# SampCreateNewHandle(_SAMP_CLIENT_INFO *,void *,_SAMP_CLIENT_INFO * *)

- ea: `0x180005e90`
- end: `0x180005f95`
- name: `?SampCreateNewHandle@@YAJPEAU_SAMP_CLIENT_INFO@@PEAXPEAPEAU1@@Z`
- size: `261`
- prototype: `int(struct _SAMP_CLIENT_INFO *, void *, struct _SAMP_CLIENT_INFO **)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000d330`
- `0x18000d630`
- `0x18000d930`
- `0x18000dde0`
- `0x18000fed0`
- `0x180010170`

## callees

- `0x180005e90`
- `0x1800078c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005eb3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f2b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005eb3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f2b`
- `ntdll!RtlLengthSid` at `0x180005f1c`
- `ntdll!RtlLengthSid` at `0x180005f1c`
- `ntdll!RtlCopySid` at `0x180005f42`
- `ntdll!RtlCopySid` at `0x180005f42`

## pseudocode

```c
__int64 __fastcall SampCreateNewHandle(struct _SAMP_CLIENT_INFO *a1, void *a2, struct _SAMP_CLIENT_INFO **a3)
{
  _QWORD *v6; // rbx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  void *v9; // rcx
  ULONG v10; // ebp
  HLOCAL v11; // rax

  *a3 = 0;
  v6 = LocalAlloc(0x40u, 0x18u);
  if ( v6 )
  {
    v9 = 0;
    *(_OWORD *)v6 = 0;
    v6[2] = 0;
    if ( a1 )
    {
      v6[1] = *((_QWORD *)a1 + 1);
      if ( *((_QWORD *)a1 + 2) )
        v9 = (void *)*((_QWORD *)a1 + 2);
    }
    if ( a2 || (a2 = v9) != 0 )
    {
      v10 = RtlLengthSid(a2);
      v11 = LocalAlloc(0x40u, v10);
      v6[2] = v11;
      if ( !v11 )
      {
        LocalFree(v6);
        v7 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          return 3221225495LL;
        v8 = 45;
        goto LABEL_16;
      }
      RtlCopySid(v10, v11, a2);
    }
    *a3 = (struct _SAMP_CLIENT_INFO *)v6;
    return 0;
  }
  v7 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    return 3221225495LL;
  v8 = 44;
LABEL_16:
  WPP_SF_(v7[2], v8, &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids);
  return 3221225495LL;
}

```

## disassembly

```asm
0x180005e90  push    rbx
0x180005e92  push    rbp
0x180005e93  push    rsi
0x180005e94  push    rdi
0x180005e95  sub     rsp, 28h
0x180005e99  mov     rdi, rdx
0x180005e9c  mov     qword ptr [r8], 0
0x180005ea3  mov     rbp, rcx
0x180005ea6  mov     edx, 18h; uBytes
0x180005eab  mov     ecx, 40h ; '@'; uFlags
0x180005eb0  mov     rsi, r8
0x180005eb3  call    cs:__imp_LocalAlloc
0x180005eb9  mov     rbx, rax
0x180005ebc  test    rax, rax
0x180005ebf  jnz     short loc_180005EE6
0x180005ec1  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ec8  test    byte ptr [rcx+1Ch], 2
0x180005ecc  jz      loc_180005F87
0x180005ed2  cmp     byte ptr [rcx+19h], 2
0x180005ed6  jb      loc_180005F87
0x180005edc  mov     edx, 2Ch ; ','
0x180005ee1  jmp     loc_180005F77
0x180005ee6  xor     eax, eax
0x180005ee8  xor     ecx, ecx
0x180005eea  xorps   xmm0, xmm0
0x180005eed  movups  xmmword ptr [rbx], xmm0
0x180005ef0  mov     [rbx+10h], rax
0x180005ef4  test    rbp, rbp
0x180005ef7  jz      short loc_180005F0C
0x180005ef9  mov     rax, [rbp+8]
0x180005efd  mov     [rbx+8], rax
0x180005f01  mov     rax, [rbp+10h]
0x180005f05  test    rax, rax
0x180005f08  cmovnz  rcx, rax
0x180005f0c  test    rdi, rdi
0x180005f0f  jnz     short loc_180005F19
0x180005f11  mov     rdi, rcx
0x180005f14  test    rcx, rcx
0x180005f17  jz      short loc_180005F48
0x180005f19  mov     rcx, rdi; Sid
0x180005f1c  call    cs:__imp_RtlLengthSid
0x180005f22  mov     edx, eax; uBytes
0x180005f24  mov     ecx, 40h ; '@'; uFlags
0x180005f29  mov     ebp, eax
0x180005f2b  call    cs:__imp_LocalAlloc
0x180005f31  mov     [rbx+10h], rax
0x180005f35  test    rax, rax
0x180005f38  jz      short loc_180005F56
0x180005f3a  mov     r8, rdi; SourceSid
0x180005f3d  mov     rdx, rax; DestinationSid
0x180005f40  mov     ecx, ebp; DestinationSidLength
0x180005f42  call    cs:__imp_RtlCopySid
0x180005f48  mov     [rsi], rbx
0x180005f4b  xor     eax, eax
0x180005f4d  add     rsp, 28h
0x180005f51  pop     rdi
0x180005f52  pop     rsi
0x180005f53  pop     rbp
0x180005f54  pop     rbx
0x180005f55  retn
0x180005f56  mov     rcx, rbx; hMem
0x180005f59  call    cs:__imp_LocalFree
0x180005f5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f66  test    byte ptr [rcx+1Ch], 2
0x180005f6a  jz      short loc_180005F87
0x180005f6c  cmp     byte ptr [rcx+19h], 2
0x180005f70  jb      short loc_180005F87
0x180005f72  mov     edx, 2Dh ; '-'
0x180005f77  mov     rcx, [rcx+10h]
0x180005f7b  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x180005f82  call    WPP_SF_
0x180005f87  mov     eax, 0C0000017h
0x180005f8c  add     rsp, 28h
0x180005f90  pop     rdi
0x180005f91  pop     rsi
0x180005f92  pop     rbp
0x180005f93  pop     rbx
0x180005f94  retn
```
