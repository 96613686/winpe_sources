# CUrlDownload_BSC::GetBindInfo(ulong *,_tagBINDINFO *)

- ea: `0x180006b70`
- end: `0x180006c59`
- name: `?GetBindInfo@CUrlDownload_BSC@@UEAAJPEAKPEAU_tagBINDINFO@@@Z`
- size: `233`
- prototype: `int(CUrlDownload_BSC *__hidden this, unsigned int *, struct _tagBINDINFO *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006b70`
- `0x18002924e`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180006c0c`
- `ole32!CoTaskMemAlloc` at `0x180006c0c`

## pseudocode

```c
__int64 __fastcall CUrlDownload_BSC::GetBindInfo(CUrlDownload_BSC *this, unsigned int *a2, struct _tagBINDINFO *a3)
{
  unsigned int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rcx
  ULONG cbSize; // ebx
  WCHAR *v9; // rax

  if ( !a2 || !a3 || !a3->cbSize )
    return 2147942487LL;
  v5 = 2051;
  *a2 = 2051;
  if ( *((_QWORD *)this + 6) )
  {
    v5 = 2115;
    *a2 = 2115;
  }
  v6 = *((_QWORD *)this + 10);
  if ( v6 && *(_DWORD *)(v6 + 744) )
  {
    v5 |= 0x200u;
    *a2 = v5;
  }
  v7 = *((_QWORD *)this + 10);
  if ( v7 )
  {
    if ( (*(_DWORD *)(v7 + 760) & 0x10000000) != 0 )
      *a2 = v5 | 8;
  }
  cbSize = a3->cbSize;
  memset_0(a3, 0, a3->cbSize);
  a3->cbSize = cbSize;
  a3->dwBindVerb = 0;
  if ( *((_DWORD *)this + 16) != 4 )
    return 0;
  v9 = (WCHAR *)CoTaskMemAlloc(0xAu);
  if ( v9 )
  {
    *(_QWORD *)v9 = 0x44004100450048LL;
    v9[4] = 0;
    a3->dwBindVerb = 3;
    a3->szCustomVerb = v9;
    return 0;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180006b70  mov     [rsp+arg_0], rbx
0x180006b75  mov     [rsp+arg_8], rsi
0x180006b7a  push    rdi
0x180006b7b  sub     rsp, 20h
0x180006b7f  mov     rdi, r8
0x180006b82  mov     rsi, rcx
0x180006b85  test    rdx, rdx
0x180006b88  jz      loc_180006C44
0x180006b8e  test    r8, r8
0x180006b91  jz      loc_180006C44
0x180006b97  cmp     dword ptr [r8], 0
0x180006b9b  jz      loc_180006C44
0x180006ba1  mov     eax, 803h
0x180006ba6  mov     [rdx], eax
0x180006ba8  cmp     qword ptr [rcx+30h], 0
0x180006bad  jz      short loc_180006BB6
0x180006baf  mov     eax, 843h
0x180006bb4  mov     [rdx], eax
0x180006bb6  mov     rcx, [rcx+50h]
0x180006bba  test    rcx, rcx
0x180006bbd  jz      short loc_180006BCE
0x180006bbf  cmp     dword ptr [rcx+2E8h], 0
0x180006bc6  jz      short loc_180006BCE
0x180006bc8  bts     eax, 9
0x180006bcc  mov     [rdx], eax
0x180006bce  mov     rcx, [rsi+50h]
0x180006bd2  test    rcx, rcx
0x180006bd5  jz      short loc_180006BE8
0x180006bd7  test    dword ptr [rcx+2F8h], 10000000h
0x180006be1  jz      short loc_180006BE8
0x180006be3  or      eax, 8
0x180006be6  mov     [rdx], eax
0x180006be8  mov     ebx, [r8]
0x180006beb  xor     edx, edx; Val
0x180006bed  mov     r8d, ebx; Size
0x180006bf0  mov     rcx, rdi; void *
0x180006bf3  call    memset_0
0x180006bf8  mov     [rdi], ebx
0x180006bfa  mov     dword ptr [rdi+2Ch], 0
0x180006c01  cmp     dword ptr [rsi+40h], 4
0x180006c05  jnz     short loc_180006C39
0x180006c07  mov     ecx, 0Ah; cb
0x180006c0c  call    cs:__imp_CoTaskMemAlloc
0x180006c12  test    rax, rax
0x180006c15  jz      short loc_180006C3D
0x180006c17  movsd   xmm0, cs:qword_18002DA28
0x180006c1f  movsd   qword ptr [rax], xmm0
0x180006c23  movzx   ecx, cs:word_18002DA30
0x180006c2a  mov     [rax+8], cx
0x180006c2e  mov     dword ptr [rdi+2Ch], 3
0x180006c35  mov     [rdi+30h], rax
0x180006c39  xor     eax, eax
0x180006c3b  jmp     short loc_180006C49
0x180006c3d  mov     eax, 8007000Eh
0x180006c42  jmp     short loc_180006C49
0x180006c44  mov     eax, 80070057h
0x180006c49  mov     rbx, [rsp+28h+arg_0]
0x180006c4e  mov     rsi, [rsp+28h+arg_8]
0x180006c53  add     rsp, 20h
0x180006c57  pop     rdi
0x180006c58  retn
```
