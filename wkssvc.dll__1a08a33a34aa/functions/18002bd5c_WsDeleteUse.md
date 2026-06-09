# WsDeleteUse

- ea: `0x18002bd5c`
- end: `0x18002be8a`
- name: `WsDeleteUse`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800012a0`

## callees

- `0x180008ddc`
- `0x180009110`
- `0x180009370`
- `0x18002bd5c`
- `0x180031f88`

## import_xrefs

- `ntdll!NtClose` at `0x18002be5c`
- `ntdll!NtClose` at `0x18002be5c`
- `ntdll!RtlReleaseResource` at `0x18002bdaf`
- `ntdll!RtlReleaseResource` at `0x18002be1f`
- `ntdll!RtlReleaseResource` at `0x18002bdaf`
- `ntdll!RtlReleaseResource` at `0x18002be1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002be0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002be6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002be0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002be6b`

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
  WsDeleteLinkedConnection(a3[4], (const wchar_t *)a3[2]);
  NtClose((HANDLE)a3[4]);
  LocalFree(a3);
  return 0;
}

```

## disassembly

```asm
0x18002bd5c  mov     [rsp+arg_0], rbx
0x18002bd61  mov     [rsp+arg_8], rsi
0x18002bd66  push    rdi
0x18002bd67  sub     rsp, 20h
0x18002bd6b  cmp     qword ptr [r8+10h], 0
0x18002bd70  mov     rbx, r8
0x18002bd73  mov     esi, r9d
0x18002bd76  jnz     short loc_18002BD93
0x18002bd78  test    edx, edx
0x18002bd7a  jnz     short loc_18002BD93
0x18002bd7c  mov     eax, [r8+1Ch]
0x18002bd80  sub     eax, 1
0x18002bd83  jz      short loc_18002BD93
0x18002bd85  mov     [r8+1Ch], eax
0x18002bd89  mov     rax, [r8+8]
0x18002bd8d  dec     dword ptr [rax]
0x18002bd8f  xor     edi, edi
0x18002bd91  jmp     short loc_18002BDA8
0x18002bd93  mov     r8d, edx
0x18002bd96  xor     r9d, r9d
0x18002bd99  mov     rdx, [rbx+20h]; Handle
0x18002bd9d  call    WsDeleteConnectionEx
0x18002bda2  mov     edi, eax
0x18002bda4  test    eax, eax
0x18002bda6  jz      short loc_18002BDC2
0x18002bda8  lea     rcx, Resource; Resource
0x18002bdaf  call    cs:__imp_RtlReleaseResource
0x18002bdb6  nop     dword ptr [rax+rax+00h]
0x18002bdbb  mov     eax, edi
0x18002bdbd  jmp     loc_18002BE79
0x18002bdc2  mov     r8, cs:Use
0x18002bdc9  lea     rdx, [rsi+rsi*2]
0x18002bdcd  mov     rcx, [r8+rdx*8]
0x18002bdd1  cmp     rcx, rbx
0x18002bdd4  jz      short loc_18002BDF3
0x18002bdd6  mov     rax, [rcx]
0x18002bdd9  jmp     short loc_18002BDE6
0x18002bddb  cmp     rax, rbx
0x18002bdde  jz      short loc_18002BDEB
0x18002bde0  mov     rcx, rax
0x18002bde3  mov     rax, [rax]
0x18002bde6  test    rax, rax
0x18002bde9  jnz     short loc_18002BDDB
0x18002bdeb  mov     rax, [rbx]
0x18002bdee  mov     [rcx], rax
0x18002bdf1  jmp     short loc_18002BDFA
0x18002bdf3  mov     rax, [rbx]
0x18002bdf6  mov     [r8+rdx*8], rax
0x18002bdfa  mov     rcx, [rbx+8]
0x18002bdfe  mov     eax, [rbx+1Ch]
0x18002be01  sub     [rcx], eax
0x18002be03  mov     rcx, [rbx+8]; hMem
0x18002be07  cmp     dword ptr [rcx], 0
0x18002be0a  jnz     short loc_18002BE18
0x18002be0c  call    cs:__imp_LocalFree
0x18002be13  nop     dword ptr [rax+rax+00h]
0x18002be18  lea     rcx, Resource; Resource
0x18002be1f  call    cs:__imp_RtlReleaseResource
0x18002be26  nop     dword ptr [rax+rax+00h]
0x18002be2b  mov     rdx, [rbx+30h]
0x18002be2f  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002be33  mov     rcx, [rbx+10h]
0x18002be37  xor     r8d, r8d
0x18002be3a  call    WsDeleteSymbolicLink
0x18002be3f  cmp     [rsp+28h+arg_20], 0
0x18002be44  jz      short loc_18002BE4B
0x18002be46  call    WsSendWnfNotification
0x18002be4b  mov     rdx, [rbx+10h]
0x18002be4f  mov     rcx, [rbx+20h]
0x18002be53  call    WsDeleteLinkedConnection
0x18002be58  mov     rcx, [rbx+20h]; Handle
0x18002be5c  call    cs:__imp_NtClose
0x18002be63  nop     dword ptr [rax+rax+00h]
0x18002be68  mov     rcx, rbx; hMem
0x18002be6b  call    cs:__imp_LocalFree
0x18002be72  nop     dword ptr [rax+rax+00h]
0x18002be77  xor     eax, eax
0x18002be79  mov     rbx, [rsp+28h+arg_0]
0x18002be7e  mov     rsi, [rsp+28h+arg_8]
0x18002be83  add     rsp, 20h
0x18002be87  pop     rdi
0x18002be88  retn
```
