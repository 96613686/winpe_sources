# CUString::HrGetCOM(ushort * *)

- ea: `0x180026420`
- end: `0x180026508`
- name: `?HrGetCOM@CUString@@QEBAJPEAPEAG@Z`
- size: `232`
- prototype: `__int64 __fastcall(CUString *__hidden this, unsigned __int16 **)`
- caller_count: `7`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005df0`
- `0x180008920`
- `0x180008e1c`
- `0x18000e7d0`
- `0x1800254b0`
- `0x18004b600`
- `0x18004b810`

## callees

- `0x180026420`
- `0x18003a798`
- `0x18003b1cc`
- `0x180045b90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026457`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026457`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800264f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800264f5`

## pseudocode

```c
__int64 __fastcall CUString::HrGetCOM(CUString *this, LPVOID *a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax
  size_t v5; // rsi
  unsigned __int16 *v6; // rax
  size_t v7; // r8
  size_t v8; // rdx
  wchar_t *v9; // rcx
  HRESULT v10; // ebx
  size_t *v11; // r8
  const wchar_t *v12; // r9
  bool v13; // zf
  size_t v15; // [rsp+20h] [rbp-38h]

  if ( a2 )
  {
    v3 = *(_QWORD *)this;
    if ( v3 )
    {
      v4 = -1;
      do
        ++v4;
      while ( *(_WORD *)(v3 + 2 * v4) );
    }
    else
    {
      v4 = 0;
    }
    v5 = v4 + 1;
    v6 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v4 + 1));
    *a2 = v6;
    if ( !v6 )
    {
      v10 = -2147024882;
      goto LABEL_13;
    }
    v10 = StringValidateDestW(v6, v5, v7);
    if ( v10 < 0 )
    {
      if ( v5 )
      {
        *v9 = 0;
LABEL_19:
        CoTaskMemFree(*a2);
        v13 = v10 == 0;
        *a2 = 0;
LABEL_9:
        if ( v13 )
          return (unsigned int)v10;
LABEL_13:
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            WPP_a0ae7d175179382b7ee5ae7e1ec9cc2a_Traceguids,
            (unsigned int)v10);
        return (unsigned int)v10;
      }
    }
    else
    {
      v10 = StringCopyWorkerW(v9, v8, v11, v12, v15);
    }
    v13 = v10 == 0;
    if ( v10 >= 0 )
      goto LABEL_9;
    goto LABEL_19;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180026420  push    rbx
0x180026422  push    rbp
0x180026423  push    rsi
0x180026424  push    rdi
0x180026425  sub     rsp, 38h
0x180026429  xor     ebp, ebp
0x18002642b  mov     rdi, rdx
0x18002642e  mov     rbx, rcx
0x180026431  test    rdx, rdx
0x180026434  jz      short loc_1800264A3
0x180026436  mov     rcx, [rcx]
0x180026439  test    rcx, rcx
0x18002643c  jz      loc_1800264E2
0x180026442  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026446  inc     rax
0x180026449  cmp     [rcx+rax*2], bp
0x18002644d  jnz     short loc_180026446
0x18002644f  lea     rsi, [rax+1]
0x180026453  lea     rcx, [rsi+rsi]; cb
0x180026457  call    cs:__imp_CoTaskMemAlloc
0x18002645e  nop     dword ptr [rax+rax+00h]
0x180026463  mov     [rdi], rax
0x180026466  mov     rcx, rax; pszDest
0x180026469  test    rax, rax
0x18002646c  jz      short loc_1800264AA
0x18002646e  cmp     [rbx], rbp
0x180026471  lea     r9, dword_180064F1C
0x180026478  mov     rdx, rsi; cchDest
0x18002647b  cmovnz  r9, [rbx]
0x18002647f  call    StringValidateDestW
0x180026484  mov     ebx, eax
0x180026486  test    eax, eax
0x180026488  js      short loc_1800264EA
0x18002648a  call    StringCopyWorkerW
0x18002648f  mov     ebx, eax
0x180026491  test    ebx, ebx
0x180026493  js      short loc_1800264F2
0x180026495  jnz     short loc_1800264AF
0x180026497  mov     eax, ebx
0x180026499  add     rsp, 38h
0x18002649d  pop     rdi
0x18002649e  pop     rsi
0x18002649f  pop     rbp
0x1800264a0  pop     rbx
0x1800264a1  retn
0x1800264a3  mov     eax, 80004003h
0x1800264a8  jmp     short loc_180026499
0x1800264aa  mov     ebx, 8007000Eh
0x1800264af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800264b6  lea     rax, WPP_GLOBAL_Control
0x1800264bd  cmp     rcx, rax
0x1800264c0  jz      short loc_180026497
0x1800264c2  test    byte ptr [rcx+1Ch], 1
0x1800264c6  jz      short loc_180026497
0x1800264c8  mov     rcx, [rcx+10h]
0x1800264cc  lea     r8, WPP_a0ae7d175179382b7ee5ae7e1ec9cc2a_Traceguids
0x1800264d3  mov     edx, 0Bh
0x1800264d8  mov     r9d, ebx
0x1800264db  call    WPP_SF_d
0x1800264e0  jmp     short loc_180026497
0x1800264e2  mov     rax, rbp
0x1800264e5  jmp     loc_18002644F
0x1800264ea  test    rsi, rsi
0x1800264ed  jz      short loc_180026491
0x1800264ef  mov     [rcx], bp
0x1800264f2  mov     rcx, [rdi]; pv
0x1800264f5  call    cs:__imp_CoTaskMemFree
0x1800264fc  nop     dword ptr [rax+rax+00h]
0x180026501  test    ebx, ebx
0x180026503  mov     [rdi], rbp
0x180026506  jmp     short loc_180026495
```
