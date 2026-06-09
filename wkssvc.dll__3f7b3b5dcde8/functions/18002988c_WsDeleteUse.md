# WsDeleteUse

- ea: `0x18002988c`
- end: `0x18002999b`
- name: `WsDeleteUse`
- size: `271`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800012a0`

## callees

- `0x180008734`
- `0x180008a4c`
- `0x180008c90`
- `0x18002988c`
- `0x18002f320`

## import_xrefs

- `ntdll!NtClose` at `0x18002997a`
- `ntdll!NtClose` at `0x18002997a`
- `ntdll!RtlReleaseResource` at `0x1800298df`
- `ntdll!RtlReleaseResource` at `0x180029943`
- `ntdll!RtlReleaseResource` at `0x1800298df`
- `ntdll!RtlReleaseResource` at `0x180029943`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029936`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029983`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029936`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029983`

## pseudocode

```c
__int64 __fastcall WsDeleteUse(struct _LUID *a1, DWORD a2, _QWORD *a3, unsigned int a4, char a5)
{
  __int64 v6; // rsi
  unsigned int v7; // edi
  _QWORD **v9; // rcx
  _QWORD *i; // rax
  _DWORD *v11; // rcx

  v6 = a4;
  if ( !a3[2] && !a2 && *((_DWORD *)a3 + 7) != 1 )
  {
    --*((_DWORD *)a3 + 7);
    --*(_DWORD *)a3[1];
    v7 = 0;
LABEL_6:
    RtlReleaseResource(&Resource);
    return v7;
  }
  v7 = WsDeleteConnectionEx(a1, (HANDLE)a3[4], a2, 0);
  if ( v7 )
    goto LABEL_6;
  v9 = *(_QWORD ***)(Use + 24 * v6);
  if ( v9 == a3 )
  {
    *(_QWORD *)(Use + 24 * v6) = *a3;
  }
  else
  {
    for ( i = *v9; i && i != a3; i = (_QWORD *)*i )
      v9 = (_QWORD **)i;
    *v9 = (_QWORD *)*a3;
  }
  *(_DWORD *)a3[1] -= *((_DWORD *)a3 + 7);
  v11 = (_DWORD *)a3[1];
  if ( !*v11 )
    LocalFree(v11);
  RtlReleaseResource(&Resource);
  WsDeleteSymbolicLink(a3[2], (const WCHAR *)a3[6], 0, (void *)0xFFFFFFFFFFFFFFFFLL);
  if ( a5 )
    WsSendWnfNotification();
  WsDeleteLinkedConnection((void *)a3[4], (const wchar_t *)a3[2]);
  NtClose((HANDLE)a3[4]);
  LocalFree(a3);
  return 0;
}

```

## disassembly

```asm
0x18002988c  mov     [rsp+arg_0], rbx
0x180029891  mov     [rsp+arg_8], rsi
0x180029896  push    rdi
0x180029897  sub     rsp, 20h
0x18002989b  cmp     qword ptr [r8+10h], 0
0x1800298a0  mov     rbx, r8
0x1800298a3  mov     esi, r9d
0x1800298a6  jnz     short loc_1800298C3
0x1800298a8  test    edx, edx
0x1800298aa  jnz     short loc_1800298C3
0x1800298ac  mov     eax, [r8+1Ch]
0x1800298b0  sub     eax, 1
0x1800298b3  jz      short loc_1800298C3
0x1800298b5  mov     [r8+1Ch], eax
0x1800298b9  mov     rax, [r8+8]
0x1800298bd  dec     dword ptr [rax]
0x1800298bf  xor     edi, edi
0x1800298c1  jmp     short loc_1800298D8
0x1800298c3  mov     r8d, edx
0x1800298c6  xor     r9d, r9d
0x1800298c9  mov     rdx, [rbx+20h]; Handle
0x1800298cd  call    WsDeleteConnectionEx
0x1800298d2  mov     edi, eax
0x1800298d4  test    eax, eax
0x1800298d6  jz      short loc_1800298EC
0x1800298d8  lea     rcx, Resource; Resource
0x1800298df  call    cs:__imp_RtlReleaseResource
0x1800298e5  mov     eax, edi
0x1800298e7  jmp     loc_18002998B
0x1800298ec  mov     r8, cs:Use
0x1800298f3  lea     rdx, [rsi+rsi*2]
0x1800298f7  mov     rcx, [r8+rdx*8]
0x1800298fb  cmp     rcx, rbx
0x1800298fe  jz      short loc_18002991D
0x180029900  mov     rax, [rcx]
0x180029903  jmp     short loc_180029910
0x180029905  cmp     rax, rbx
0x180029908  jz      short loc_180029915
0x18002990a  mov     rcx, rax
0x18002990d  mov     rax, [rax]
0x180029910  test    rax, rax
0x180029913  jnz     short loc_180029905
0x180029915  mov     rax, [rbx]
0x180029918  mov     [rcx], rax
0x18002991b  jmp     short loc_180029924
0x18002991d  mov     rax, [rbx]
0x180029920  mov     [r8+rdx*8], rax
0x180029924  mov     rcx, [rbx+8]
0x180029928  mov     eax, [rbx+1Ch]
0x18002992b  sub     [rcx], eax
0x18002992d  mov     rcx, [rbx+8]; hMem
0x180029931  cmp     dword ptr [rcx], 0
0x180029934  jnz     short loc_18002993C
0x180029936  call    cs:__imp_LocalFree
0x18002993c  lea     rcx, Resource; Resource
0x180029943  call    cs:__imp_RtlReleaseResource
0x180029949  mov     rdx, [rbx+30h]
0x18002994d  or      r9, 0FFFFFFFFFFFFFFFFh
0x180029951  mov     rcx, [rbx+10h]
0x180029955  xor     r8d, r8d
0x180029958  call    WsDeleteSymbolicLink
0x18002995d  cmp     [rsp+28h+arg_20], 0
0x180029962  jz      short loc_180029969
0x180029964  call    WsSendWnfNotification
0x180029969  mov     rdx, [rbx+10h]
0x18002996d  mov     rcx, [rbx+20h]
0x180029971  call    WsDeleteLinkedConnection
0x180029976  mov     rcx, [rbx+20h]; Handle
0x18002997a  call    cs:__imp_NtClose
0x180029980  mov     rcx, rbx; hMem
0x180029983  call    cs:__imp_LocalFree
0x180029989  xor     eax, eax
0x18002998b  mov     rbx, [rsp+28h+arg_0]
0x180029990  mov     rsi, [rsp+28h+arg_8]
0x180029995  add     rsp, 20h
0x180029999  pop     rdi
0x18002999a  retn
```
