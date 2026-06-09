# DavParseData

- ea: `0x180028584`
- end: `0x18002867a`
- name: `DavParseData`
- size: `246`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x1800049bc`
- `0x18001507c`
- `0x18001a5a0`
- `0x18001ad0c`
- `0x18001dcb4`
- `0x1800206bc`
- `0x1800229b0`

## callees

- `0x18000b89c`
- `0x180027800`
- `0x180028584`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800285e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002863b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800285e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002863b`

## pseudocode

```c
__int64 __fastcall DavParseData(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  int v6; // esi
  DWORD CurrentThreadId; // eax

  *(_QWORD *)(a2 + 16) = a1;
  *(_QWORD *)(a2 + 48) = a1;
  *(_DWORD *)(a2 + 40) = 0;
  *(_DWORD *)(a1 + 4) = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a3 + 192LL))(a3, 0xFFFFFFFFLL);
  if ( v6 >= 0 )
  {
    DavOverrideAttributes(*(struct _DAV_FILE_ATTRIBUTES **)(a2 + 48));
    *a4 = *(_DWORD *)(a2 + 40);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids,
        CurrentThreadId,
        v6);
    }
    return 87;
  }
}

```

## disassembly

```asm
0x180028584  mov     [rsp+arg_0], rbx
0x180028589  mov     [rsp+arg_8], rsi
0x18002858e  push    rdi
0x18002858f  sub     rsp, 30h
0x180028593  mov     rdi, r9
0x180028596  mov     rbx, rdx
0x180028599  mov     [rdx+10h], rcx
0x18002859d  mov     [rdx+30h], rcx
0x1800285a1  mov     dword ptr [rdx+28h], 0
0x1800285a8  mov     dword ptr [rcx+4], 0
0x1800285af  mov     rax, [r8]
0x1800285b2  or      edx, 0FFFFFFFFh
0x1800285b5  mov     rcx, r8
0x1800285b8  mov     rax, [rax+0C0h]
0x1800285bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285c4  mov     esi, eax
0x1800285c6  test    eax, eax
0x1800285c8  jns     short loc_18002860E
0x1800285ca  lea     rax, WPP_GLOBAL_Control
0x1800285d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285d8  cmp     rcx, rax
0x1800285db  jz      short loc_18002860C
0x1800285dd  test    byte ptr [rcx+1Ch], 8
0x1800285e1  jz      short loc_18002860C
0x1800285e3  call    cs:__imp_GetCurrentThreadId
0x1800285e9  mov     edx, 2Dh ; '-'
0x1800285ee  mov     [rsp+38h+var_18], esi
0x1800285f2  mov     r9d, eax
0x1800285f5  lea     r8, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids
0x1800285fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180028603  mov     rcx, [rcx+10h]
0x180028607  call    WPP_SF_Dd
0x18002860c  jmp     short loc_180028665
0x18002860e  mov     rcx, [rbx+30h]; struct _DAV_FILE_ATTRIBUTES *
0x180028612  call    ?DavOverrideAttributes@@YAXPEAU_DAV_FILE_ATTRIBUTES@@@Z; DavOverrideAttributes(_DAV_FILE_ATTRIBUTES *)
0x180028617  mov     ecx, [rbx+28h]
0x18002861a  mov     [rdi], ecx
0x18002861c  xor     eax, eax
0x18002861e  jmp     short loc_18002866A
0x180028620  mov     ebx, eax
0x180028622  lea     rax, WPP_GLOBAL_Control
0x180028629  mov     rcx, cs:WPP_GLOBAL_Control
0x180028630  cmp     rcx, rax
0x180028633  jz      short loc_180028665
0x180028635  test    byte ptr [rcx+1Ch], 8
0x180028639  jz      short loc_180028665
0x18002863b  call    cs:__imp_GetCurrentThreadId
0x180028641  mov     edx, 2Eh ; '.'
0x180028646  mov     [rsp+38h+var_18], ebx
0x18002864a  mov     r9d, eax
0x18002864d  lea     r8, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids
0x180028654  mov     rcx, cs:WPP_GLOBAL_Control
0x18002865b  mov     rcx, [rcx+10h]
0x18002865f  call    WPP_SF_Dd
0x180028664  nop
0x180028665  mov     eax, 57h ; 'W'
0x18002866a  mov     rbx, [rsp+38h+arg_0]
0x18002866f  mov     rsi, [rsp+38h+arg_8]
0x180028674  add     rsp, 30h
0x180028678  pop     rdi
0x180028679  retn
```
