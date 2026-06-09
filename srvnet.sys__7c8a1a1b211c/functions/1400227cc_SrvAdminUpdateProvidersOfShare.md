# SrvAdminUpdateProvidersOfShare

- ea: `0x1400227cc`
- end: `0x14002296a`
- name: `SrvAdminUpdateProvidersOfShare`
- size: `414`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140005570`
- `0x14000ed94`
- `0x140023ae0`
- `0x140023f90`
- `0x140025990`
- `0x140025b80`

## callees

- `0x14000ef40`
- `0x140013af0`
- `0x1400227cc`
- `0x140022a90`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14002283b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002283b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400227f3`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400227f3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140022952`
- `ntoskrnl!ExReleaseResourceLite` at `0x140022952`

## pseudocode

```c
__int64 __fastcall SrvAdminUpdateProvidersOfShare(_DWORD *a1, ULONG a2)
{
  __int64 v4; // rax
  int v5; // esi
  struct _UNICODE_STRING *v6; // rbx
  int v7; // r8d
  void *v9; // [rsp+38h] [rbp-40h]
  struct _IO_STATUS_BLOCK v10; // [rsp+40h] [rbp-38h] BYREF

  v10 = 0;
  ExAcquireResourceSharedLite(&ProviderLock, 1u);
  v4 = RfsTableEnumerate(hProviderTable);
  v5 = -1063780347;
  while ( v4 )
  {
    v6 = (struct _UNICODE_STRING *)(v4 + 24);
    if ( !a1[38] || RtlEqualUnicodeString((PCUNICODE_STRING)(v4 + 24), &Srv2DeviceName, 1u) )
    {
      v5 = SrvAdminIssueFsctl(v6, a2, a1, 0xF0u, 0, 0, &v10, v9);
      if ( v5 < 0 )
      {
        if ( a2 == 2261007 )
          break;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_DZZd(
            WPP_GLOBAL_Control->AttachedDevice,
            (_DWORD)a1 + 8,
            v7,
            a2,
            (__int64)(a1 + 2),
            (__int64)(a1 + 6),
            v5);
        }
      }
    }
    v4 = RfsTableEnumerate(hProviderTable);
  }
  ExReleaseResourceLite(&ProviderLock);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400227cc  mov     rax, rsp
0x1400227cf  push    rbx
0x1400227d0  push    rbp
0x1400227d1  push    rsi
0x1400227d2  push    rdi
0x1400227d3  sub     rsp, 58h
0x1400227d7  mov     ebp, edx
0x1400227d9  mov     dword ptr [rax+18h], 0
0x1400227e0  mov     rdi, rcx
0x1400227e3  xorps   xmm0, xmm0
0x1400227e6  mov     dl, 1; Wait
0x1400227e8  lea     rcx, ProviderLock; Resource
0x1400227ef  movups  xmmword ptr [rax-38h], xmm0
0x1400227f3  call    cs:__imp_ExAcquireResourceSharedLite
0x1400227fa  nop     dword ptr [rax+rax+00h]
0x1400227ff  mov     rcx, cs:hProviderTable; SpinLock
0x140022806  lea     rdx, [rsp+78h+arg_10]
0x14002280e  call    RfsTableEnumerate
0x140022813  mov     esi, 0C0980005h
0x140022818  test    rax, rax
0x14002281b  jz      loc_14002294B
0x140022821  cmp     dword ptr [rdi+98h], 0
0x140022828  lea     rbx, [rax+18h]
0x14002282c  jz      short loc_14002284B
0x14002282e  mov     r8b, 1; CaseInSensitive
0x140022831  lea     rdx, Srv2DeviceName; String2
0x140022838  mov     rcx, rbx; String1
0x14002283b  call    cs:__imp_RtlEqualUnicodeString
0x140022842  nop     dword ptr [rax+rax+00h]
0x140022847  test    al, al
0x140022849  jz      short loc_1400228CA
0x14002284b  lea     rax, [rsp+78h+var_38]
0x140022850  mov     r9d, 0F0h
0x140022856  mov     [rsp+78h+var_48], rax
0x14002285b  mov     r8, rdi
0x14002285e  mov     dword ptr [rsp+78h+var_50], 0
0x140022866  mov     edx, ebp
0x140022868  mov     rcx, rbx
0x14002286b  mov     [rsp+78h+var_58], 0
0x140022874  call    SrvAdminIssueFsctl
0x140022879  mov     esi, eax
0x14002287b  test    eax, eax
0x14002287d  jns     short loc_1400228CA
0x14002287f  cmp     ebp, 22800Fh
0x140022885  jz      short loc_1400228E3
0x140022887  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002288e  lea     rax, WPP_GLOBAL_Control
0x140022895  cmp     rcx, rax
0x140022898  jz      short loc_1400228CA
0x14002289a  mov     edx, [rcx+2Ch]
0x14002289d  test    dl, 20h
0x1400228a0  jz      short loc_1400228CA
0x1400228a2  cmp     byte ptr [rcx+29h], 2
0x1400228a6  jb      short loc_1400228CA
0x1400228a8  mov     rcx, [rcx+18h]
0x1400228ac  lea     rax, [rdi+18h]
0x1400228b0  lea     rdx, [rdi+8]
0x1400228b4  mov     dword ptr [rsp+78h+var_48], esi
0x1400228b8  mov     [rsp+78h+var_50], rax
0x1400228bd  mov     r9d, ebp
0x1400228c0  mov     [rsp+78h+var_58], rdx
0x1400228c5  call    WPP_SF_DZZd
0x1400228ca  mov     rcx, cs:hProviderTable; SpinLock
0x1400228d1  lea     rdx, [rsp+78h+arg_10]
0x1400228d9  call    RfsTableEnumerate
0x1400228de  jmp     loc_140022818
0x1400228e3  mov     ebx, [rsp+78h+arg_10]
0x1400228ea  xor     eax, eax
0x1400228ec  mov     [rsp+78h+arg_10], eax
0x1400228f3  cmp     eax, ebx
0x1400228f5  jz      short loc_14002294B
0x1400228f7  mov     rcx, cs:hProviderTable; SpinLock
0x1400228fe  lea     rdx, [rsp+78h+arg_10]
0x140022906  call    RfsTableEnumerate
0x14002290b  test    rax, rax
0x14002290e  jz      short loc_14002294B
0x140022910  lea     rcx, [rax+18h]
0x140022914  mov     r9d, 0F0h
0x14002291a  lea     rax, [rsp+78h+var_38]
0x14002291f  mov     r8, rdi
0x140022922  mov     [rsp+78h+var_48], rax
0x140022927  mov     edx, 228017h
0x14002292c  mov     dword ptr [rsp+78h+var_50], 0
0x140022934  mov     [rsp+78h+var_58], 0
0x14002293d  call    SrvAdminIssueFsctl
0x140022942  mov     eax, [rsp+78h+arg_10]
0x140022949  jmp     short loc_1400228F3
0x14002294b  lea     rcx, ProviderLock; Resource
0x140022952  call    cs:__imp_ExReleaseResourceLite
0x140022959  nop     dword ptr [rax+rax+00h]
0x14002295e  mov     eax, esi
0x140022960  add     rsp, 58h
0x140022964  pop     rdi
0x140022965  pop     rsi
0x140022966  pop     rbp
0x140022967  pop     rbx
0x140022968  retn
```
