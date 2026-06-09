# UtilGetReportIdFromReportPath(wchar_t const * const)

- ea: `0x14001acd8`
- end: `0x14001ad3d`
- name: `?UtilGetReportIdFromReportPath@@YAPEB_WQEB_W@Z`
- size: `101`
- prototype: `const wchar_t *__fastcall(const wchar_t *const)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140005f98`
- `0x14001a8bc`

## callees

- `0x14000e380`
- `0x14001acd8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14001acea`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14001acea`

## pseudocode

```c
wchar_t *__fastcall UtilGetReportIdFromReportPath(const wchar_t *a1)
{
  wchar_t *v2; // rax
  wchar_t *v3; // rbx

  v2 = wcsrchr(a1, 0x5Fu);
  v3 = v2;
  if ( v2 )
    return v2 + 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, &WPP_5958ded8188d3319535ef35cd392335c_Traceguids, a1);
  return v3;
}

```

## disassembly

```asm
0x14001acd8  mov     [rsp+arg_0], rbx
0x14001acdd  push    rdi
0x14001acde  sub     rsp, 20h
0x14001ace2  mov     edx, 5Fh ; '_'; Ch
0x14001ace7  mov     rdi, rcx
0x14001acea  call    cs:__imp_wcsrchr
0x14001acf0  mov     rbx, rax
0x14001acf3  test    rax, rax
0x14001acf6  jz      short loc_14001ACFE
0x14001acf8  add     rbx, 2
0x14001acfc  jmp     short loc_14001AD2F
0x14001acfe  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ad05  lea     rax, WPP_GLOBAL_Control
0x14001ad0c  cmp     rcx, rax
0x14001ad0f  jz      short loc_14001AD2F
0x14001ad11  test    byte ptr [rcx+1Ch], 1
0x14001ad15  jz      short loc_14001AD2F
0x14001ad17  mov     rcx, [rcx+10h]
0x14001ad1b  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x14001ad22  mov     edx, 6Ah ; 'j'
0x14001ad27  mov     r9, rdi
0x14001ad2a  call    WPP_SF_S
0x14001ad2f  mov     rax, rbx
0x14001ad32  mov     rbx, [rsp+28h+arg_0]
0x14001ad37  add     rsp, 20h
0x14001ad3b  pop     rdi
0x14001ad3c  retn
```
