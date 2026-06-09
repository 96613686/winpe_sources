# ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::GrowBuffer(unsigned __int64)

- ea: `0x18000fa90`
- end: `0x18000fb58`
- name: `?GrowBuffer@?$CAtlArray@V?$CComPtr@VCUICommand@@@ATL@@V?$CElementTraits@V?$CComPtr@VCUICommand@@@ATL@@@2@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011418`

## callees

- `0x180004c00`
- `0x18000fa90`

## import_xrefs

- `msvcrt!calloc` at `0x18000facb`
- `msvcrt!calloc` at `0x18000fb06`
- `msvcrt!calloc` at `0x18000facb`
- `msvcrt!calloc` at `0x18000fb06`
- `msvcrt!memmove_s` at `0x18000fb29`
- `msvcrt!memmove_s` at `0x18000fb29`
- `msvcrt!free` at `0x18000fb39`
- `msvcrt!free` at `0x18000fb39`

## pseudocode

```c
char __fastcall ATL::CAtlArray<ATL::CComPtr<CUICommand>,ATL::CElementTraits<ATL::CComPtr<CUICommand>>>::GrowBuffer(
        __int64 a1,
        size_t a2)
{
  size_t v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rax
  void *v8; // rsi
  errno_t v10; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 <= v4 )
    return 1;
  v5 = *(int *)(a1 + 24);
  if ( !*(_QWORD *)a1 )
  {
    if ( v5 > a2 )
      a2 = v5;
    v6 = calloc(a2, 8u);
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
  v7 = calloc(a2, 8u);
  v8 = v7;
  if ( !v7 )
    return 0;
  v10 = memmove_s(v7, 8LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 8LL * *(_QWORD *)(a1 + 8));
  ATL::AtlCrtErrorCheck(v10);
  free(*(void **)a1);
  *(_QWORD *)a1 = v8;
LABEL_15:
  *(_QWORD *)(a1 + 16) = a2;
  return 1;
}

```

## disassembly

```asm
0x18000fa90  mov     [rsp+arg_0], rbx
0x18000fa95  mov     [rsp+arg_8], rsi
0x18000fa9a  push    rdi
0x18000fa9b  sub     rsp, 20h
0x18000fa9f  mov     rbx, rdx
0x18000faa2  mov     rdi, rcx
0x18000faa5  mov     rdx, [rcx+10h]
0x18000faa9  cmp     rbx, rdx
0x18000faac  jbe     loc_18000FB46
0x18000fab2  cmp     qword ptr [rdi], 0
0x18000fab6  movsxd  rcx, dword ptr [rcx+18h]
0x18000faba  jnz     short loc_18000FADB
0x18000fabc  cmp     rcx, rbx
0x18000fabf  mov     edx, 8; Size
0x18000fac4  cmova   rbx, rcx
0x18000fac8  mov     rcx, rbx; Count
0x18000facb  call    cs:__imp_calloc
0x18000fad1  mov     [rdi], rax
0x18000fad4  test    rax, rax
0x18000fad7  jz      short loc_18000FB14
0x18000fad9  jmp     short loc_18000FB42
0x18000fadb  test    rcx, rcx
0x18000fade  jnz     short loc_18000FAF3
0x18000fae0  mov     rcx, rdx
0x18000fae3  mov     rax, rbx
0x18000fae6  shr     rcx, 1
0x18000fae9  sub     rax, rdx
0x18000faec  cmp     rax, rcx
0x18000faef  cmova   rcx, rax
0x18000faf3  lea     rax, [rdx+rcx]
0x18000faf7  mov     edx, 8; Size
0x18000fafc  cmp     rbx, rax
0x18000faff  cmovb   rbx, rax
0x18000fb03  mov     rcx, rbx; Count
0x18000fb06  call    cs:__imp_calloc
0x18000fb0c  mov     rsi, rax
0x18000fb0f  test    rax, rax
0x18000fb12  jnz     short loc_18000FB18
0x18000fb14  xor     al, al
0x18000fb16  jmp     short loc_18000FB48
0x18000fb18  mov     rdx, [rdi+8]
0x18000fb1c  mov     rcx, rsi; Destination
0x18000fb1f  mov     r8, [rdi]; Source
0x18000fb22  shl     rdx, 3; DestinationSize
0x18000fb26  mov     r9, rdx; SourceSize
0x18000fb29  call    cs:__imp_memmove_s
0x18000fb2f  mov     ecx, eax; int
0x18000fb31  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000fb36  mov     rcx, [rdi]; Block
0x18000fb39  call    cs:__imp_free
0x18000fb3f  mov     [rdi], rsi
0x18000fb42  mov     [rdi+10h], rbx
0x18000fb46  mov     al, 1
0x18000fb48  mov     rbx, [rsp+28h+arg_0]
0x18000fb4d  mov     rsi, [rsp+28h+arg_8]
0x18000fb52  add     rsp, 20h
0x18000fb56  pop     rdi
0x18000fb57  retn
```
