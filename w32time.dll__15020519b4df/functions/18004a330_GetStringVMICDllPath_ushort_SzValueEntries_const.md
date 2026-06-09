# GetStringVMICDllPath(ushort * *,SzValueEntries const *)

- ea: `0x18004a330`
- end: `0x18004a3c4`
- name: `?GetStringVMICDllPath@@YAJPEAPEAGPEBUSzValueEntries@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(unsigned __int16 **, const struct SzValueEntries *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000bde0`
- `0x1800299e0`
- `0x18004a330`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004a37b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004a37b`

## string_xrefs

- `0x18004a344`: `%SystemRoot%\System32\vmictimeprovider.dll`
- `0x18004a397`: `%SystemRoot%\System32\vmictimeprovider.dll`

## pseudocode

```c
__int64 __fastcall GetStringVMICDllPath(unsigned __int16 **a1, const struct SzValueEntries *a2)
{
  int v3; // r8d
  unsigned __int64 v4; // rbx
  unsigned __int16 *v5; // rax
  unsigned __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v7 = 0;
  v3 = StringCchLengthW(L"%SystemRoot%\\System32\\vmictimeprovider.dll", 0x103u, &v7);
  if ( v3 >= 0 )
  {
    v4 = v7 + 1;
    v5 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v7 + 1));
    *a1 = v5;
    if ( v5 )
    {
      v3 = StringCchCopyW(v5, v4, L"%SystemRoot%\\System32\\vmictimeprovider.dll");
      if ( v3 >= 0 )
        return 0;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18004a330  mov     [rsp+arg_8], rbx
0x18004a335  push    rdi
0x18004a336  sub     rsp, 20h
0x18004a33a  mov     rdi, rcx
0x18004a33d  mov     qword ptr [rcx], 0
0x18004a344  lea     rcx, aSystemrootSyst_2; "%SystemRoot%\\System32\\vmictimeprovide"...
0x18004a34b  mov     [rsp+28h+arg_0], 0
0x18004a354  lea     r8, [rsp+28h+arg_0]; unsigned __int64 *
0x18004a359  mov     edx, 103h; unsigned __int64
0x18004a35e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004a363  mov     r8d, eax
0x18004a366  test    eax, eax
0x18004a368  js      short loc_18004A3B5
0x18004a36a  mov     rbx, [rsp+28h+arg_0]
0x18004a36f  mov     ecx, 40h ; '@'; uFlags
0x18004a374  inc     rbx
0x18004a377  lea     rdx, [rbx+rbx]; uBytes
0x18004a37b  call    cs:__imp_LocalAlloc
0x18004a382  nop     dword ptr [rax+rax+00h]
0x18004a387  mov     [rdi], rax
0x18004a38a  test    rax, rax
0x18004a38d  jnz     short loc_18004A397
0x18004a38f  mov     r8d, 8007000Eh
0x18004a395  jmp     short loc_18004A3B5
0x18004a397  lea     r8, aSystemrootSyst_2; "%SystemRoot%\\System32\\vmictimeprovide"...
0x18004a39e  mov     rdx, rbx; unsigned __int64
0x18004a3a1  mov     rcx, rax; unsigned __int16 *
0x18004a3a4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004a3a9  mov     r8d, eax
0x18004a3ac  xor     eax, eax
0x18004a3ae  test    r8d, r8d
0x18004a3b1  cmovns  r8d, eax
0x18004a3b5  mov     rbx, [rsp+28h+arg_8]
0x18004a3ba  mov     eax, r8d
0x18004a3bd  add     rsp, 20h
0x18004a3c1  pop     rdi
0x18004a3c2  retn
```
