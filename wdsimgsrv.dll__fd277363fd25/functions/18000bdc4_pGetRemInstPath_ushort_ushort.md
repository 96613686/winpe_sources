# pGetRemInstPath(ushort *,ushort * *)

- ea: `0x18000bdc4`
- end: `0x18000beda`
- name: `?pGetRemInstPath@@YAKPEAGPEAPEAG@Z`
- size: `278`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007120`

## callees

- `0x180006d10`
- `0x18000aa2c`
- `0x18000bdc4`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000bea6`
- `KERNEL32!HeapFree` at `0x18000bea6`
- `KERNEL32!HeapAlloc` at `0x18000be27`
- `KERNEL32!HeapAlloc` at `0x18000be27`
- `KERNEL32!GetProcessHeap` at `0x18000be10`
- `KERNEL32!GetProcessHeap` at `0x18000be92`
- `KERNEL32!GetProcessHeap` at `0x18000be10`
- `KERNEL32!GetProcessHeap` at `0x18000be92`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000be80`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000be80`

## pseudocode

```c
__int64 __fastcall pGetRemInstPath(unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned int v4; // edi
  __int64 v5; // rsi
  size_t v6; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rbx
  HRESULT v10; // eax
  HANDLE v11; // rax

  v4 = 0;
  if ( a1 && a2 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a1[v5] );
    v6 = v5 + 11;
    ProcessHeap = GetProcessHeap();
    v8 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * v6);
    v9 = v8;
    if ( v8 )
    {
      v10 = StringCchCopyW(v8, v6, (size_t *)L"\\\\");
      if ( (v10 < 0 || (v10 = StringCchCatW(v9, v6, a1), v10 < 0)
                    || (v10 = StringCchCatW(v9, v6, L"\\Reminst"), v10 < 0))
        && (v4 = WIN32_FROM_HRESULT(v10)) != 0 )
      {
        v11 = GetProcessHeap();
        HeapFree(v11, 0, v9);
      }
      else
      {
        *a2 = v9;
      }
    }
    else
    {
      return 8;
    }
  }
  else
  {
    return 87;
  }
  return v4;
}

```

## disassembly

```asm
0x18000bdc4  mov     [rsp+arg_0], rbx
0x18000bdc9  mov     [rsp+arg_8], rbp
0x18000bdce  mov     [rsp+arg_10], rsi
0x18000bdd3  push    rdi
0x18000bdd4  push    r14
0x18000bdd6  push    r15
0x18000bdd8  sub     rsp, 20h
0x18000bddc  xor     r15d, r15d
0x18000bddf  mov     r14, rdx
0x18000bde2  mov     rbp, rcx
0x18000bde5  mov     edi, r15d
0x18000bde8  test    rcx, rcx
0x18000bdeb  jz      loc_18000BEB9
0x18000bdf1  test    rdx, rdx
0x18000bdf4  jz      loc_18000BEB9
0x18000bdfa  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000bdfe  inc     rsi
0x18000be01  cmp     [rcx+rsi*2], r15w
0x18000be06  jnz     short loc_18000BDFE
0x18000be08  add     rsi, 0Bh
0x18000be0c  lea     rbx, [rsi+rsi]
0x18000be10  call    cs:__imp_GetProcessHeap
0x18000be17  nop     dword ptr [rax+rax+00h]
0x18000be1c  mov     r8, rbx; dwBytes
0x18000be1f  mov     edx, 8; dwFlags
0x18000be24  mov     rcx, rax; hHeap
0x18000be27  call    cs:__imp_HeapAlloc
0x18000be2e  nop     dword ptr [rax+rax+00h]
0x18000be33  mov     rbx, rax
0x18000be36  test    rax, rax
0x18000be39  jnz     short loc_18000BE40
0x18000be3b  lea     edi, [rax+8]
0x18000be3e  jmp     short loc_18000BEBE
0x18000be40  lea     r8, asc_18001CE7C; "\\\\"
0x18000be47  mov     rdx, rsi; unsigned __int64
0x18000be4a  mov     rcx, rbx; unsigned __int16 *
0x18000be4d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000be52  test    eax, eax
0x18000be54  js      short loc_18000BE7E
0x18000be56  mov     r8, rbp; unsigned __int16 *
0x18000be59  mov     rdx, rsi; unsigned __int64
0x18000be5c  mov     rcx, rbx; unsigned __int16 *
0x18000be5f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000be64  test    eax, eax
0x18000be66  js      short loc_18000BE7E
0x18000be68  lea     r8, aReminst; "\\Reminst"
0x18000be6f  mov     rdx, rsi; unsigned __int64
0x18000be72  mov     rcx, rbx; unsigned __int16 *
0x18000be75  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000be7a  test    eax, eax
0x18000be7c  jns     short loc_18000BEB4
0x18000be7e  mov     ecx, eax
0x18000be80  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000be87  nop     dword ptr [rax+rax+00h]
0x18000be8c  mov     edi, eax
0x18000be8e  test    eax, eax
0x18000be90  jz      short loc_18000BEB4
0x18000be92  call    cs:__imp_GetProcessHeap
0x18000be99  nop     dword ptr [rax+rax+00h]
0x18000be9e  mov     r8, rbx; lpMem
0x18000bea1  xor     edx, edx; dwFlags
0x18000bea3  mov     rcx, rax; hHeap
0x18000bea6  call    cs:__imp_HeapFree
0x18000bead  nop     dword ptr [rax+rax+00h]
0x18000beb2  jmp     short loc_18000BEBE
0x18000beb4  mov     [r14], rbx
0x18000beb7  jmp     short loc_18000BEBE
0x18000beb9  mov     edi, 57h ; 'W'
0x18000bebe  mov     rbx, [rsp+38h+arg_0]
0x18000bec3  mov     eax, edi
0x18000bec5  mov     rbp, [rsp+38h+arg_8]
0x18000beca  mov     rsi, [rsp+38h+arg_10]
0x18000becf  add     rsp, 20h
0x18000bed3  pop     r15
0x18000bed5  pop     r14
0x18000bed7  pop     rdi
0x18000bed8  retn
```
