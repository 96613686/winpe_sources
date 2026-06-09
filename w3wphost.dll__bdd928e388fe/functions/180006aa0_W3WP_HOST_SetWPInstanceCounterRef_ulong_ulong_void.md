# W3WP_HOST::SetWPInstanceCounterRef(ulong,ulong,void *)

- ea: `0x180006aa0`
- end: `0x180006b67`
- name: `?SetWPInstanceCounterRef@W3WP_HOST@@UEAAJKKPEAX@Z`
- size: `199`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this, unsigned int, unsigned int, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006aa0`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x180006af8`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterRefValue` at `0x180006af8`
- `iisutil!PuDbgPrintError` at `0x180006b52`
- `iisutil!PuDbgPrintError` at `0x180006b52`

## string_xrefs

- `0x180006b38`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::SetWPInstanceCounterRef(W3WP_HOST *this, int a2, ULONG a3, void *a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rcx
  struct _PERF_COUNTERSET_INSTANCE *v9; // rdx
  void *v10; // rcx
  __int64 v11; // rcx
  signed int v12; // eax

  if ( !*(_DWORD *)(*((_QWORD *)this + 33) + 88LL) && a4 )
  {
    v7 = 0;
    if ( *((_DWORD *)this + 18) )
    {
      if ( !a2 )
      {
        v8 = *((_QWORD *)this + 8);
        v9 = *(struct _PERF_COUNTERSET_INSTANCE **)(v8 + 32);
        v10 = *(void **)v8;
        goto LABEL_8;
      }
      if ( a2 == 1 )
      {
        v11 = *((_QWORD *)this + 8);
        v9 = *(struct _PERF_COUNTERSET_INSTANCE **)(v11 + 56);
        v10 = *(void **)(v11 + 8);
LABEL_8:
        v12 = PerfSetCounterRefValue(v10, v9, a3, a4);
        if ( v12 )
        {
          if ( v12 > 0 )
            v7 = (unsigned __int16)v12 | 0x80070000;
          else
            v7 = v12;
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
              1477,
              "W3WP_HOST::SetWPInstanceCounterRef",
              v7,
              "PerfSetCounterRefValue() failed for setId=%d, counterId=%d, ref=%p.\n",
              a2,
              a3,
              a4);
        }
      }
    }
    return v7;
  }
  return 0;
}

```

## disassembly

```asm
0x180006aa0  push    rbx
0x180006aa2  push    rbp
0x180006aa3  push    rsi
0x180006aa4  push    rdi
0x180006aa5  sub     rsp, 58h
0x180006aa9  mov     rax, [rcx+108h]
0x180006ab0  mov     rdi, r9
0x180006ab3  mov     ebp, r8d
0x180006ab6  mov     esi, edx
0x180006ab8  cmp     dword ptr [rax+58h], 0
0x180006abc  jnz     loc_180006B5C
0x180006ac2  test    r9, r9
0x180006ac5  jz      loc_180006B5C
0x180006acb  xor     ebx, ebx
0x180006acd  cmp     [rcx+48h], ebx
0x180006ad0  jz      loc_180006B58
0x180006ad6  test    edx, edx
0x180006ad8  jnz     short loc_180006AE7
0x180006ada  mov     rcx, [rcx+40h]
0x180006ade  mov     rdx, [rcx+20h]
0x180006ae2  mov     rcx, [rcx]
0x180006ae5  jmp     short loc_180006AF8
0x180006ae7  cmp     esi, 1
0x180006aea  jnz     short loc_180006B58
0x180006aec  mov     rcx, [rcx+40h]
0x180006af0  mov     rdx, [rcx+38h]; Instance
0x180006af4  mov     rcx, [rcx+8]; Provider
0x180006af8  call    cs:__imp_PerfSetCounterRefValue
0x180006afe  test    eax, eax
0x180006b00  jz      short loc_180006B58
0x180006b02  jg      short loc_180006B08
0x180006b04  mov     ebx, eax
0x180006b06  jmp     short loc_180006B11
0x180006b08  movzx   ebx, ax
0x180006b0b  or      ebx, 80070000h
0x180006b11  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006b18  jz      short loc_180006B58
0x180006b1a  mov     rcx, cs:g_pDebug
0x180006b21  lea     rax, aPerfsetcounter; "PerfSetCounterRefValue() failed for set"...
0x180006b28  mov     [rsp+78h+var_38], rdi
0x180006b2d  lea     r9, aW3wpHostSetwpi; "W3WP_HOST::SetWPInstanceCounterRef"
0x180006b34  mov     [rsp+78h+var_40], ebp
0x180006b38  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006b3f  mov     [rsp+78h+var_48], esi
0x180006b43  mov     r8d, 5C5h
0x180006b49  mov     [rsp+78h+var_50], rax
0x180006b4e  mov     [rsp+78h+var_58], ebx
0x180006b52  call    cs:__imp_PuDbgPrintError
0x180006b58  mov     eax, ebx
0x180006b5a  jmp     short loc_180006B5E
0x180006b5c  xor     eax, eax
0x180006b5e  add     rsp, 58h
0x180006b62  pop     rdi
0x180006b63  pop     rsi
0x180006b64  pop     rbp
0x180006b65  pop     rbx
0x180006b66  retn
```
