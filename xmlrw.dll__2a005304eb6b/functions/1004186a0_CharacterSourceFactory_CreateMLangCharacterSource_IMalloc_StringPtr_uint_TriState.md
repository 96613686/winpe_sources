# CharacterSourceFactory::CreateMLangCharacterSource(IMalloc *,StringPtr *,uint,TriState)

- ea: `0x1004186a0`
- end: `0x1004187b3`
- name: `?CreateMLangCharacterSource@CharacterSourceFactory@@CAPEAVCharacterSource@@PEAUIMalloc@@PEAUStringPtr@@IW4TriState@@@Z`
- size: `275`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x10040ded0`
- `0x10040ee90`
- `0x1004182b0`

## callees

- `0x100401520`
- `0x100401780`
- `0x1004186a0`
- `0x10041b8a0`
- `0x10041b970`
- `0x100423dd0`
- `0x1004394f0`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1004186ec`
- `KERNEL32!HeapAlloc` at `0x1004186ec`

## pseudocode

```c
MlangCharacterSource *__fastcall CharacterSourceFactory::CreateMLangCharacterSource(
        struct IMalloc *a1,
        __int64 a2,
        unsigned int a3)
{
  struct IMalloc *v5; // rbx
  MlangCharacterSource *v6; // rax
  MlangCharacterSource *v7; // rbx
  unsigned int v8; // eax
  int v9; // eax

  v5 = a1;
  if ( a1 || (a1 = g_pMalloc) != 0 )
    v6 = (MlangCharacterSource *)((__int64 (__fastcall *)(struct IMalloc *, __int64))a1->lpVtbl->Alloc)(a1, 272);
  else
    v6 = (MlangCharacterSource *)HeapAlloc(g_hHeap, 0, 0x110u);
  if ( !v6 )
  {
    MXRRaiseException(-2147024882);
    goto LABEL_15;
  }
  *((_QWORD *)v6 + 1) = v5;
  v7 = MlangCharacterSource::MlangCharacterSource(v6, v5);
  v8 = *(_DWORD *)(a2 + 8);
  if ( v8 != dword_100450B38 || (v9 = memcmp(*(const void **)a2, CodeStringPtr::empty, 2LL * v8)) != 0 )
    LOBYTE(v9) = 1;
  if ( !(_BYTE)v9 )
  {
    if ( !CanConvertToUnicode(a3) )
    {
      *((_DWORD *)v7 + 67) = 0;
      *((_DWORD *)v7 + 62) = a3;
      return v7;
    }
LABEL_15:
    MXRRaiseException(-1072894462);
    __debugbreak();
    JUMPOUT(0x1004187B3LL);
  }
  MlangCharacterSource::Init(v7, (struct StringPtr *)a2);
  return v7;
}

```

## disassembly

```asm
0x1004186a0  mov     [rsp+arg_8], rbx
0x1004186a5  mov     [rsp+arg_10], rsi
0x1004186aa  push    rdi
0x1004186ab  sub     rsp, 40h
0x1004186af  mov     esi, r8d
0x1004186b2  mov     rdi, rdx
0x1004186b5  mov     rbx, rcx
0x1004186b8  test    rcx, rcx
0x1004186bb  jnz     short loc_1004186C9
0x1004186bd  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004186c4  test    rcx, rcx
0x1004186c7  jz      short loc_1004186DD
0x1004186c9  mov     rax, [rcx]
0x1004186cc  mov     edx, 110h
0x1004186d1  mov     rax, [rax+18h]
0x1004186d5  call    cs:__guard_dispatch_icall_fptr
0x1004186db  jmp     short loc_1004186F2
0x1004186dd  xor     edx, edx; dwFlags
0x1004186df  mov     r8d, 110h; dwBytes
0x1004186e5  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004186ec  call    cs:__imp_HeapAlloc
0x1004186f2  test    rax, rax
0x1004186f5  jz      loc_10041879C
0x1004186fb  mov     [rax+8], rbx
0x1004186ff  mov     rdx, rbx; struct IMalloc *
0x100418702  mov     rcx, rax; this
0x100418705  call    ??0MlangCharacterSource@@QEAA@PEAUIMalloc@@@Z; MlangCharacterSource::MlangCharacterSource(IMalloc *)
0x10041870a  mov     rbx, rax
0x10041870d  mov     [rsp+48h+arg_0], rax
0x100418712  mov     eax, [rdi+8]
0x100418715  cmp     eax, cs:dword_100450B38
0x10041871b  jnz     short loc_100418736
0x10041871d  mov     r8d, eax
0x100418720  add     r8, r8; Size
0x100418723  mov     rdx, cs:?empty@CodeStringPtr@@2UStringPtr@@A; Buf2
0x10041872a  mov     rcx, [rdi]; Buf1
0x10041872d  call    memcmp
0x100418732  test    eax, eax
0x100418734  jz      short loc_100418738
0x100418736  mov     al, 1
0x100418738  test    al, al
0x10041873a  jz      short loc_100418749
0x10041873c  mov     rdx, rdi; struct StringPtr *
0x10041873f  mov     rcx, rbx; this
0x100418742  call    ?Init@MlangCharacterSource@@QEAAXPEAUStringPtr@@@Z; MlangCharacterSource::Init(StringPtr *)
0x100418747  jmp     short loc_100418764
0x100418749  mov     ecx, esi; unsigned int
0x10041874b  call    ?CanConvertToUnicode@@YAJI@Z; CanConvertToUnicode(uint)
0x100418750  test    eax, eax
0x100418752  jnz     short loc_1004187A7
0x100418754  mov     dword ptr [rbx+10Ch], 0
0x10041875e  mov     [rbx+0F8h], esi
0x100418764  mov     rax, rbx
0x100418767  mov     rbx, [rsp+48h+arg_8]
0x10041876c  mov     rsi, [rsp+48h+arg_10]
0x100418771  add     rsp, 40h
0x100418775  pop     rdi
0x100418776  retn
0x100418777  mov     rcx, [rsp+48h+arg_0]
0x10041877c  test    rcx, rcx
0x10041877f  jz      short loc_100418792
0x100418781  mov     rax, [rcx]
0x100418784  mov     edx, 1
0x100418789  mov     rax, [rax]
0x10041878c  call    cs:__guard_dispatch_icall_fptr
0x100418792  mov     ecx, [rsp+48h+var_28]; int
0x100418796  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10041879b  nop
0x10041879c  mov     ecx, 8007000Eh; int
0x1004187a1  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004187a6  nop
0x1004187a7  mov     ecx, 0C00CEE02h; int
0x1004187ac  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004187b1  nop
0x1004187b2  int     3; Trap to Debugger
0x100439f20  push    rbp
0x100439f22  sub     rsp, 20h
0x100439f26  mov     rbp, rdx
0x100439f29  mov     [rbp+38h], rcx
0x100439f2d  mov     [rbp+30h], rcx
0x100439f31  mov     rax, [rbp+30h]
0x100439f35  mov     rcx, [rax]
0x100439f38  mov     [rbp+28h], rcx
0x100439f3c  mov     rax, [rbp+28h]
0x100439f40  mov     eax, [rax]
0x100439f42  cmp     eax, 0C0000005h
0x100439f47  jz      short loc_100439F79
0x100439f49  add     eax, 1FFFFFFFh
0x100439f4e  cmp     eax, 1
0x100439f51  ja      short loc_100439F69
0x100439f53  mov     rax, [rbp+28h]
0x100439f57  cmp     dword ptr [rax+18h], 1
0x100439f5b  jnz     short loc_100439F69
0x100439f5d  mov     rax, [rbp+28h]
0x100439f61  mov     ecx, [rax+20h]
0x100439f64  mov     [rbp+20h], ecx
0x100439f67  jmp     short loc_100439F70
0x100439f69  mov     dword ptr [rbp+20h], 8000FFFFh
0x100439f70  mov     dword ptr [rbp+24h], 1
0x100439f77  jmp     short loc_100439F80
0x100439f79  mov     dword ptr [rbp+24h], 0
0x100439f80  mov     eax, [rbp+24h]
0x100439f83  add     rsp, 20h
0x100439f87  pop     rbp
0x100439f88  retn
```
