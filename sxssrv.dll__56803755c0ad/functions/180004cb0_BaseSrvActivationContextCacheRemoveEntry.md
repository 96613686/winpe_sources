# BaseSrvActivationContextCacheRemoveEntry

- ea: `0x180004cb0`
- end: `0x180004e7e`
- name: `BaseSrvActivationContextCacheRemoveEntry`
- size: `462`
- prototype: `NTSTATUS __fastcall(__int128 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180003170`

## callees

- `0x180004cb0`
- `0x1800053a0`
- `0x180006c13`
- `0x180006c30`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180004ceb`
- `ntdll!RtlEnterCriticalSection` at `0x180004ceb`
- `ntdll!RtlLeaveCriticalSection` at `0x180004e46`
- `ntdll!RtlLeaveCriticalSection` at `0x180006f20`
- `ntdll!RtlLeaveCriticalSection` at `0x180004e46`
- `ntdll!RtlLeaveCriticalSection` at `0x180006f20`
- `ntdll!DbgPrintEx` at `0x180004e2e`
- `ntdll!DbgPrintEx` at `0x180004e2e`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180004d45`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180004d45`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180004e06`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180004e06`

## string_xrefs

- `0x180004e22`: `Fail to remove cache entry\n`

## pseudocode

```c
NTSTATUS __fastcall BaseSrvActivationContextCacheRemoveEntry(__int128 *a1)
{
  NTSTATUS result; // eax
  int v3; // edi
  _QWORD *v4; // rax
  _OWORD *v5; // rdx
  _OWORD **v6; // rcx
  void **v7; // rax
  __int128 Buffer; // [rsp+20h] [rbp-D8h] BYREF
  __int128 v9; // [rsp+30h] [rbp-C8h]
  __int128 v10; // [rsp+40h] [rbp-B8h]
  __int128 v11; // [rsp+50h] [rbp-A8h]
  __int128 v12; // [rsp+60h] [rbp-98h]
  __int128 v13; // [rsp+70h] [rbp-88h]
  __int128 v14; // [rsp+80h] [rbp-78h]
  __int128 v15; // [rsp+90h] [rbp-68h]
  __int128 v16; // [rsp+A0h] [rbp-58h]
  __int128 v17; // [rsp+B0h] [rbp-48h]
  __int128 v18; // [rsp+C0h] [rbp-38h]
  __int64 v19; // [rsp+D0h] [rbp-28h]

  memset_0(&Buffer, 0, 0xB8u);
  result = RtlEnterCriticalSection(&SxsActCtxCacheCS);
  v3 = result;
  if ( result >= 0 )
  {
    v9 = *a1;
    v10 = a1[1];
    v11 = a1[2];
    v12 = a1[3];
    v13 = a1[4];
    v14 = a1[5];
    v4 = RtlLookupElementGenericTableAvl(g_SxsActCtxCache, &Buffer);
    v5 = v4;
    if ( v4 )
    {
      v6 = (_OWORD **)*v4;
      v7 = (void **)v4[1];
      if ( v6[1] != v5 || *v7 != v5 )
        __fastfail(3u);
      *v7 = v6;
      v6[1] = v7;
      Buffer = *v5;
      v9 = v5[1];
      v10 = v5[2];
      v11 = v5[3];
      v12 = v5[4];
      v13 = v5[5];
      v14 = v5[6];
      v15 = v5[7];
      v16 = v5[8];
      v17 = v5[9];
      v18 = v5[10];
      v19 = *((_QWORD *)v5 + 22);
      if ( RtlDeleteElementGenericTableAvl(g_SxsActCtxCache, v5) )
      {
        BaseSrvActivationContextCacheFreeEntry(&Buffer);
      }
      else
      {
        DbgPrintEx(0x33u, 0, "Fail to remove cache entry\n");
        v3 = -1073741271;
      }
    }
    else
    {
      v3 = -1073741275;
    }
    RtlLeaveCriticalSection(&SxsActCtxCacheCS);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180004cb0  mov     [rsp+arg_8], rbx
0x180004cb5  push    rdi
0x180004cb6  sub     rsp, 0F0h
0x180004cbd  mov     rax, cs:__security_cookie
0x180004cc4  xor     rax, rsp
0x180004cc7  mov     [rsp+0F8h+var_18], rax
0x180004ccf  mov     rbx, rcx
0x180004cd2  xor     edx, edx; Val
0x180004cd4  mov     r8d, 0B8h; Size
0x180004cda  lea     rcx, [rsp+0F8h+Buffer]; void *
0x180004cdf  call    memset_0
0x180004ce4  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x180004ceb  call    cs:__imp_RtlEnterCriticalSection
0x180004cf2  nop     dword ptr [rax+rax+00h]
0x180004cf7  mov     edi, eax
0x180004cf9  test    eax, eax
0x180004cfb  js      loc_180004E54
0x180004d01  movaps  xmm0, xmmword ptr [rbx]
0x180004d04  movaps  [rsp+0F8h+var_C8], xmm0
0x180004d09  movaps  xmm1, xmmword ptr [rbx+10h]
0x180004d0d  movaps  [rsp+0F8h+var_B8], xmm1
0x180004d12  movaps  xmm0, xmmword ptr [rbx+20h]
0x180004d16  movaps  [rsp+0F8h+var_A8], xmm0
0x180004d1b  movaps  xmm1, xmmword ptr [rbx+30h]
0x180004d1f  movaps  [rsp+0F8h+var_98], xmm1
0x180004d24  movaps  xmm0, xmmword ptr [rbx+40h]
0x180004d28  movaps  [rsp+0F8h+var_88], xmm0
0x180004d2d  movaps  xmm1, xmmword ptr [rbx+50h]
0x180004d31  movaps  [rsp+0F8h+var_78], xmm1
0x180004d39  lea     rdx, [rsp+0F8h+Buffer]; Buffer
0x180004d3e  mov     rcx, cs:g_SxsActCtxCache; Table
0x180004d45  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180004d4c  nop     dword ptr [rax+rax+00h]
0x180004d51  mov     rdx, rax; Buffer
0x180004d54  test    rax, rax
0x180004d57  jnz     short loc_180004D63
0x180004d59  mov     edi, 0C0000225h
0x180004d5e  jmp     loc_180004E3F
0x180004d63  mov     rcx, [rax]
0x180004d66  mov     rax, [rax+8]
0x180004d6a  cmp     [rcx+8], rdx
0x180004d6e  jnz     loc_180004E76
0x180004d74  cmp     [rax], rdx
0x180004d77  jnz     loc_180004E76
0x180004d7d  mov     [rax], rcx
0x180004d80  mov     [rcx+8], rax
0x180004d84  lea     rcx, [rsp+0F8h+Buffer]
0x180004d89  movups  xmm0, xmmword ptr [rdx]
0x180004d8c  movups  xmmword ptr [rcx], xmm0
0x180004d8f  movups  xmm1, xmmword ptr [rdx+10h]
0x180004d93  movups  xmmword ptr [rcx+10h], xmm1
0x180004d97  movups  xmm0, xmmword ptr [rdx+20h]
0x180004d9b  movups  xmmword ptr [rcx+20h], xmm0
0x180004d9f  movups  xmm1, xmmword ptr [rdx+30h]
0x180004da3  movups  xmmword ptr [rcx+30h], xmm1
0x180004da7  movups  xmm0, xmmword ptr [rdx+40h]
0x180004dab  movups  xmmword ptr [rcx+40h], xmm0
0x180004daf  movups  xmm1, xmmword ptr [rdx+50h]
0x180004db3  movups  xmmword ptr [rcx+50h], xmm1
0x180004db7  movups  xmm0, xmmword ptr [rdx+60h]
0x180004dbb  movups  xmmword ptr [rcx+60h], xmm0
0x180004dbf  movups  xmm0, xmmword ptr [rdx+70h]
0x180004dc3  movups  xmmword ptr [rcx+70h], xmm0
0x180004dc7  movups  xmm1, xmmword ptr [rdx+80h]
0x180004dce  movups  xmmword ptr [rcx+80h], xmm1
0x180004dd5  movups  xmm0, xmmword ptr [rdx+90h]
0x180004ddc  movups  xmmword ptr [rcx+90h], xmm0
0x180004de3  movups  xmm1, xmmword ptr [rdx+0A0h]
0x180004dea  movups  xmmword ptr [rcx+0A0h], xmm1
0x180004df1  mov     rax, [rdx+0B0h]
0x180004df8  mov     [rcx+0B0h], rax
0x180004dff  mov     rcx, cs:g_SxsActCtxCache; Table
0x180004e06  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180004e0d  nop     dword ptr [rax+rax+00h]
0x180004e12  test    al, al
0x180004e14  jz      short loc_180004E22
0x180004e16  lea     rcx, [rsp+0F8h+Buffer]
0x180004e1b  call    BaseSrvActivationContextCacheFreeEntry
0x180004e20  jmp     short loc_180004E3F
0x180004e22  lea     r8, aFailToRemoveCa; "Fail to remove cache entry\n"
0x180004e29  xor     edx, edx; Level
0x180004e2b  lea     ecx, [rdx+33h]; ComponentId
0x180004e2e  call    cs:__imp_DbgPrintEx
0x180004e35  nop     dword ptr [rax+rax+00h]
0x180004e3a  mov     edi, 0C0000229h
0x180004e3f  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x180004e46  call    cs:__imp_RtlLeaveCriticalSection
0x180004e4d  nop     dword ptr [rax+rax+00h]
0x180004e52  mov     eax, edi
0x180004e54  mov     rcx, [rsp+0F8h+var_18]
0x180004e5c  xor     rcx, rsp; StackCookie
0x180004e5f  call    __security_check_cookie
0x180004e64  mov     rbx, [rsp+0F8h+arg_8]
0x180004e6c  add     rsp, 0F0h
0x180004e73  pop     rdi
0x180004e74  retn
0x180004e76  mov     ecx, 3
0x180004e7b  int     29h; Win8: RtlFailFast(ecx)
0x180006f10  push    rbp
0x180006f12  sub     rsp, 20h
0x180006f16  mov     rbp, rdx
0x180006f19  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x180006f20  call    cs:__imp_RtlLeaveCriticalSection
0x180006f27  nop     dword ptr [rax+rax+00h]
0x180006f2c  nop
0x180006f2d  add     rsp, 20h
0x180006f31  pop     rbp
0x180006f32  retn
```
