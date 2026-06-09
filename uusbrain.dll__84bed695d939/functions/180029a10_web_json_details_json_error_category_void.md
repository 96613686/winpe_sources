# web::json::details::json_error_category(void)

- ea: `0x180029a10`
- end: `0x180029a72`
- name: `?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ`
- size: `98`
- prototype: `const struct web::json::details::json_error_category_impl *__fastcall(web::json::details *__hidden this)`
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e198`
- `0x18002e6b0`
- `0x18002f6a4`
- `0x18003008c`
- `0x180030358`
- `0x180030674`
- `0x180030844`
- `0x180030b24`

## callees

- `0x180029a10`
- `0x180042ba4`
- `0x1800430d0`
- `0x180043138`

## pseudocode

```c
void ***__fastcall web::json::details::json_error_category(web::json::details *this)
{
  if ( dword_180063B30 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180063B30);
    if ( dword_180063B30 == -1 )
    {
      atexit(web::json::details::json_error_category_::_2_::_dynamic_atexit_destructor_for__instance__);
      Init_thread_footer(&dword_180063B30);
    }
  }
  return &off_180062150;
}

```

## disassembly

```asm
0x180029a10  sub     rsp, 28h
0x180029a14  mov     ecx, cs:_tls_index
0x180029a1a  mov     rax, gs:58h
0x180029a23  mov     edx, 4
0x180029a28  mov     rax, [rax+rcx*8]
0x180029a2c  mov     eax, [rdx+rax]
0x180029a2f  cmp     cs:dword_180063B30, eax
0x180029a35  jg      short loc_180029A43
0x180029a37  lea     rax, off_180062150
0x180029a3e  add     rsp, 28h
0x180029a42  retn
0x180029a43  lea     rcx, dword_180063B30
0x180029a4a  call    _Init_thread_header
0x180029a4f  cmp     cs:dword_180063B30, 0FFFFFFFFh
0x180029a56  jnz     short loc_180029A37
0x180029a58  lea     rcx, _web__json__details__json_error_category____2____dynamic_atexit_destructor_for__instance__; void (__cdecl *)()
0x180029a5f  call    atexit
0x180029a64  lea     rcx, dword_180063B30
0x180029a6b  call    _Init_thread_footer
0x180029a70  jmp     short loc_180029A37
```
