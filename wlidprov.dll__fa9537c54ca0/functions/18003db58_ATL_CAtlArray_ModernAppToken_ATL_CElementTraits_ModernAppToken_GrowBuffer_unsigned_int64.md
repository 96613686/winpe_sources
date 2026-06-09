# ATL::CAtlArray<_ModernAppToken,ATL::CElementTraits<_ModernAppToken>>::GrowBuffer(unsigned __int64)

- ea: `0x18003db58`
- end: `0x18003dc24`
- name: `?GrowBuffer@?$CAtlArray@U_ModernAppToken@@V?$CElementTraits@U_ModernAppToken@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003ea04`

## callees

- `0x180015788`
- `0x18003db58`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18003dbf5`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18003dbf5`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18003db93`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18003dbce`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18003db93`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18003dbce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003dc05`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003dc05`

## pseudocode

```c
char __fastcall ATL::CAtlArray<_ModernAppToken,ATL::CElementTraits<_ModernAppToken>>::GrowBuffer(__int64 a1, size_t a2)
{
  size_t v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rsi
  errno_t v9; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 <= v4 )
    return 1;
  v5 = *(int *)(a1 + 24);
  if ( !*(_QWORD *)a1 )
  {
    if ( v5 > a2 )
      a2 = v5;
    v6 = calloc(a2, 0x30u);
    *(_QWORD *)a1 = v6;
    if ( v6 )
      goto LABEL_15;
    return 0;
  }
  if ( !v5 )
  {
    v5 = v4 >> 1;
    if ( a2 - v4 > v4 >> 1 )
      v5 = a2 - v4;
  }
  if ( a2 < v4 + v5 )
    a2 = v4 + v5;
  v7 = calloc(a2, 0x30u);
  if ( !v7 )
    return 0;
  v9 = memmove_s(v7, 48LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 48LL * *(_QWORD *)(a1 + 8));
  ATL::AtlCrtErrorCheck(v9);
  free(*(void **)a1);
  *(_QWORD *)a1 = v7;
LABEL_15:
  *(_QWORD *)(a1 + 16) = a2;
  return 1;
}

```

## disassembly

```asm
0x18003db58  mov     [rsp+arg_0], rbx
0x18003db5d  mov     [rsp+arg_8], rsi
0x18003db62  push    rdi
0x18003db63  sub     rsp, 20h
0x18003db67  mov     rdi, rdx
0x18003db6a  mov     rbx, rcx
0x18003db6d  mov     rdx, [rcx+10h]
0x18003db71  cmp     rdi, rdx
0x18003db74  jbe     loc_18003DC12
0x18003db7a  cmp     qword ptr [rbx], 0
0x18003db7e  movsxd  rcx, dword ptr [rcx+18h]
0x18003db82  jnz     short loc_18003DBA3
0x18003db84  cmp     rcx, rdi
0x18003db87  mov     edx, 30h ; '0'; Size
0x18003db8c  cmova   rdi, rcx
0x18003db90  mov     rcx, rdi; Count
0x18003db93  call    cs:__imp_calloc
0x18003db99  mov     [rbx], rax
0x18003db9c  test    rax, rax
0x18003db9f  jz      short loc_18003DBDC
0x18003dba1  jmp     short loc_18003DC0E
0x18003dba3  test    rcx, rcx
0x18003dba6  jnz     short loc_18003DBBB
0x18003dba8  mov     rcx, rdx
0x18003dbab  mov     rax, rdi
0x18003dbae  shr     rcx, 1
0x18003dbb1  sub     rax, rdx
0x18003dbb4  cmp     rax, rcx
0x18003dbb7  cmova   rcx, rax
0x18003dbbb  lea     rax, [rdx+rcx]
0x18003dbbf  mov     edx, 30h ; '0'; Size
0x18003dbc4  cmp     rdi, rax
0x18003dbc7  cmovb   rdi, rax
0x18003dbcb  mov     rcx, rdi; Count
0x18003dbce  call    cs:__imp_calloc
0x18003dbd4  mov     rsi, rax
0x18003dbd7  test    rax, rax
0x18003dbda  jnz     short loc_18003DBE0
0x18003dbdc  xor     al, al
0x18003dbde  jmp     short loc_18003DC14
0x18003dbe0  mov     rax, [rbx+8]
0x18003dbe4  mov     rcx, rsi; Destination
0x18003dbe7  mov     r8, [rbx]; Source
0x18003dbea  lea     rdx, [rax+rax*2]
0x18003dbee  shl     rdx, 4; DestinationSize
0x18003dbf2  mov     r9, rdx; SourceSize
0x18003dbf5  call    cs:__imp_memmove_s
0x18003dbfb  mov     ecx, eax; int
0x18003dbfd  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18003dc02  mov     rcx, [rbx]; Block
0x18003dc05  call    cs:__imp_free
0x18003dc0b  mov     [rbx], rsi
0x18003dc0e  mov     [rbx+10h], rdi
0x18003dc12  mov     al, 1
0x18003dc14  mov     rbx, [rsp+28h+arg_0]
0x18003dc19  mov     rsi, [rsp+28h+arg_8]
0x18003dc1e  add     rsp, 20h
0x18003dc22  pop     rdi
0x18003dc23  retn
```
