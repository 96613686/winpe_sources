# BaseSrvActivationContextCacheRemoveEntry

- ea: `0x180004e60`
- end: `0x18000503e`
- name: `BaseSrvActivationContextCacheRemoveEntry`
- size: `478`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180003310`

## callees

- `0x180004e60`
- `0x180005580`
- `0x180006ccd`
- `0x180006cf0`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180004e9b`
- `ntdll!RtlEnterCriticalSection` at `0x180004e9b`
- `ntdll!RtlLeaveCriticalSection` at `0x180005006`
- `ntdll!RtlLeaveCriticalSection` at `0x180006fe0`
- `ntdll!RtlLeaveCriticalSection` at `0x180005006`
- `ntdll!RtlLeaveCriticalSection` at `0x180006fe0`
- `ntdll!DbgPrintEx` at `0x180004fee`
- `ntdll!DbgPrintEx` at `0x180004fee`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180004ef5`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180004ef5`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180004fc4`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180004fc4`

## string_xrefs

- `0x180004fe0`: `Fail to remove cache entry\n`

## pseudocode

```c
NTSTATUS __fastcall BaseSrvActivationContextCacheRemoveEntry(__int128 *a1)
{
  NTSTATUS result; // eax
  int v3; // edi
  _QWORD *v4; // rax
  _QWORD *v5; // rdx
  _QWORD **v6; // rax
  void **v7; // rcx
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
      v6 = (_QWORD **)*v4;
      if ( v6[1] != v5 || (v7 = (void **)v5[1], *v7 != v5) )
        __fastfail(3u);
      *v7 = v6;
      v6[1] = v7;
      Buffer = *(_OWORD *)v5;
      v9 = *((_OWORD *)v5 + 1);
      v10 = *((_OWORD *)v5 + 2);
      v11 = *((_OWORD *)v5 + 3);
      v12 = *((_OWORD *)v5 + 4);
      v13 = *((_OWORD *)v5 + 5);
      v14 = *((_OWORD *)v5 + 6);
      v15 = *((_OWORD *)v5 + 7);
      v16 = *((_OWORD *)v5 + 8);
      v17 = *((_OWORD *)v5 + 9);
      v18 = *((_OWORD *)v5 + 10);
      v19 = v5[22];
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
0x180004e60  mov     [rsp+arg_8], rbx
0x180004e65  push    rdi
0x180004e66  sub     rsp, 0F0h
0x180004e6d  mov     rax, cs:__security_cookie
0x180004e74  xor     rax, rsp
0x180004e77  mov     [rsp+0F8h+var_18], rax
0x180004e7f  mov     rbx, rcx
0x180004e82  xor     edx, edx; Val
0x180004e84  mov     r8d, 0B8h; Size
0x180004e8a  lea     rcx, [rsp+0F8h+Buffer]; void *
0x180004e8f  call    memset_0
0x180004e94  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x180004e9b  call    cs:__imp_RtlEnterCriticalSection
0x180004ea2  nop     dword ptr [rax+rax+00h]
0x180004ea7  mov     edi, eax
0x180004ea9  test    eax, eax
0x180004eab  js      loc_180005014
0x180004eb1  movaps  xmm0, xmmword ptr [rbx]
0x180004eb4  movaps  [rsp+0F8h+var_C8], xmm0
0x180004eb9  movaps  xmm1, xmmword ptr [rbx+10h]
0x180004ebd  movaps  [rsp+0F8h+var_B8], xmm1
0x180004ec2  movaps  xmm0, xmmword ptr [rbx+20h]
0x180004ec6  movaps  [rsp+0F8h+var_A8], xmm0
0x180004ecb  movaps  xmm1, xmmword ptr [rbx+30h]
0x180004ecf  movaps  [rsp+0F8h+var_98], xmm1
0x180004ed4  movaps  xmm0, xmmword ptr [rbx+40h]
0x180004ed8  movaps  [rsp+0F8h+var_88], xmm0
0x180004edd  movaps  xmm1, xmmword ptr [rbx+50h]
0x180004ee1  movaps  [rsp+0F8h+var_78], xmm1
0x180004ee9  lea     rdx, [rsp+0F8h+Buffer]; Buffer
0x180004eee  mov     rcx, cs:g_SxsActCtxCache; Table
0x180004ef5  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180004efc  nop     dword ptr [rax+rax+00h]
0x180004f01  mov     rdx, rax; Buffer
0x180004f04  test    rax, rax
0x180004f07  jnz     short loc_180004F13
0x180004f09  mov     edi, 0C0000225h
0x180004f0e  jmp     loc_180004FFF
0x180004f13  mov     rax, [rax]
0x180004f16  cmp     [rax+8], rdx
0x180004f1a  jnz     loc_180005036
0x180004f20  mov     rcx, [rdx+8]
0x180004f24  cmp     [rcx], rdx
0x180004f27  jnz     loc_180005036
0x180004f2d  mov     [rcx], rax
0x180004f30  mov     [rax+8], rcx
0x180004f34  movups  xmm0, xmmword ptr [rdx]
0x180004f37  movups  [rsp+0F8h+Buffer], xmm0
0x180004f3c  movups  xmm1, xmmword ptr [rdx+10h]
0x180004f40  movups  [rsp+0F8h+var_C8], xmm1
0x180004f45  movups  xmm0, xmmword ptr [rdx+20h]
0x180004f49  movups  [rsp+0F8h+var_B8], xmm0
0x180004f4e  movups  xmm1, xmmword ptr [rdx+30h]
0x180004f52  movups  [rsp+0F8h+var_A8], xmm1
0x180004f57  movups  xmm0, xmmword ptr [rdx+40h]
0x180004f5b  movups  [rsp+0F8h+var_98], xmm0
0x180004f60  movups  xmm1, xmmword ptr [rdx+50h]
0x180004f64  movups  [rsp+0F8h+var_88], xmm1
0x180004f69  movups  xmm0, xmmword ptr [rdx+60h]
0x180004f6d  movups  [rsp+0F8h+var_78], xmm0
0x180004f75  movups  xmm1, xmmword ptr [rdx+70h]
0x180004f79  movups  [rsp+0F8h+var_68], xmm1
0x180004f81  movups  xmm0, xmmword ptr [rdx+80h]
0x180004f88  movups  [rsp+0F8h+var_58], xmm0
0x180004f90  movups  xmm1, xmmword ptr [rdx+90h]
0x180004f97  movups  [rsp+0F8h+var_48], xmm1
0x180004f9f  movups  xmm0, xmmword ptr [rdx+0A0h]
0x180004fa6  movups  [rsp+0F8h+var_38], xmm0
0x180004fae  mov     rax, [rdx+0B0h]
0x180004fb5  mov     [rsp+0F8h+var_28], rax
0x180004fbd  mov     rcx, cs:g_SxsActCtxCache; Table
0x180004fc4  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180004fcb  nop     dword ptr [rax+rax+00h]
0x180004fd0  test    al, al
0x180004fd2  jz      short loc_180004FE0
0x180004fd4  lea     rcx, [rsp+0F8h+Buffer]
0x180004fd9  call    BaseSrvActivationContextCacheFreeEntry
0x180004fde  jmp     short loc_180004FFF
0x180004fe0  lea     r8, aFailToRemoveCa; "Fail to remove cache entry\n"
0x180004fe7  xor     edx, edx; Level
0x180004fe9  mov     ecx, 33h ; '3'; ComponentId
0x180004fee  call    cs:__imp_DbgPrintEx
0x180004ff5  nop     dword ptr [rax+rax+00h]
0x180004ffa  mov     edi, 0C0000229h
0x180004fff  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x180005006  call    cs:__imp_RtlLeaveCriticalSection
0x18000500d  nop     dword ptr [rax+rax+00h]
0x180005012  mov     eax, edi
0x180005014  mov     rcx, [rsp+0F8h+var_18]
0x18000501c  xor     rcx, rsp; StackCookie
0x18000501f  call    __security_check_cookie
0x180005024  mov     rbx, [rsp+0F8h+arg_8]
0x18000502c  add     rsp, 0F0h
0x180005033  pop     rdi
0x180005034  retn
0x180005036  mov     ecx, 3
0x18000503b  int     29h; Win8: RtlFailFast(ecx)
0x180006fd0  push    rbp
0x180006fd2  sub     rsp, 20h
0x180006fd6  mov     rbp, rdx
0x180006fd9  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x180006fe0  call    cs:__imp_RtlLeaveCriticalSection
0x180006fe7  nop     dword ptr [rax+rax+00h]
0x180006fec  nop
0x180006fed  add     rsp, 20h
0x180006ff1  pop     rbp
0x180006ff2  retn
```
