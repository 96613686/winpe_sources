# CopyExtensionsTelemetryContext::GetInstance(void)

- ea: `0x18006fb9c`
- end: `0x18006fc43`
- name: `?GetInstance@CopyExtensionsTelemetryContext@@SAAEAV1@XZ`
- size: `167`
- prototype: `struct CopyExtensionsTelemetryContext *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800537e0`

## callees

- `0x180052c10`
- `0x18005a160`
- `0x18005b538`
- `0x18006fb9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006fc18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006fc18`

## pseudocode

```c
struct CopyExtensionsTelemetryContext *CopyExtensionsTelemetryContext::GetInstance(void)
{
  __int64 v0; // rdx
  __int64 v1; // rdi
  int v2; // eax
  DWORD CurrentProcessId; // eax

  v0 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v1 = v0 + 16;
  v2 = *(_DWORD *)(v0 + 852);
  if ( (v2 & 1) == 0 )
  {
    *(_BYTE *)(v0 + 24) = 1;
    *(_DWORD *)(v0 + 852) = v2 | 1;
    *(_QWORD *)v1 = &CopyExtensionsTelemetryContext::`vftable';
    *(_DWORD *)(v0 + 32) = *(_DWORD *)L"/0";
    *(_WORD *)(v0 + 36) = a0[2];
    memset_0((void *)(v0 + 38), 0, 0x202u);
    *(_BYTE *)(v1 + 536) = 0;
    *(_QWORD *)(v1 + 540) = 0;
    CurrentProcessId = GetCurrentProcessId();
    GetProcessImageName((unsigned __int16 *)(v1 + 16), CurrentProcessId);
    _tlregdtor(CopyExtensionsTelemetryContext::GetInstance_::_2_::_dynamic_atexit_destructor_for__instance__);
  }
  return (struct CopyExtensionsTelemetryContext *)v1;
}

```

## disassembly

```asm
0x18006fb9c  mov     [rsp+arg_0], rbx
0x18006fba1  push    rdi
0x18006fba2  sub     rsp, 20h
0x18006fba6  mov     rax, gs:58h
0x18006fbaf  mov     ecx, cs:_tls_index
0x18006fbb5  mov     r8d, 354h
0x18006fbbb  mov     edi, 10h
0x18006fbc0  mov     rdx, [rax+rcx*8]
0x18006fbc4  add     rdi, rdx
0x18006fbc7  mov     eax, [r8+rdx]
0x18006fbcb  test    al, 1
0x18006fbcd  jnz     short loc_18006FC35
0x18006fbcf  or      eax, 1
0x18006fbd2  mov     byte ptr [rdi+8], 1
0x18006fbd6  mov     [r8+rdx], eax
0x18006fbda  lea     rcx, [rdi+16h]; void *
0x18006fbde  lea     rax, ??_7CopyExtensionsTelemetryContext@@6B@; const CopyExtensionsTelemetryContext::`vftable'
0x18006fbe5  xor     edx, edx; Val
0x18006fbe7  mov     [rdi], rax
0x18006fbea  mov     r8d, 202h; Size
0x18006fbf0  mov     eax, dword ptr cs:a0; "/0"
0x18006fbf6  mov     [rdi+10h], eax
0x18006fbf9  movzx   eax, word ptr cs:a0+4; ""
0x18006fc00  mov     [rdi+14h], ax
0x18006fc04  call    memset_0
0x18006fc09  xor     eax, eax
0x18006fc0b  mov     [rdi+218h], al
0x18006fc11  mov     [rdi+21Ch], rax
0x18006fc18  call    cs:__imp_GetCurrentProcessId
0x18006fc1e  mov     edx, eax; dwProcessId
0x18006fc20  lea     rcx, [rdi+10h]; unsigned __int16 *
0x18006fc24  call    ?GetProcessImageName@@YAKPEAGK@Z; GetProcessImageName(ushort *,ulong)
0x18006fc29  lea     rcx, _CopyExtensionsTelemetryContext__GetInstance____2____dynamic_atexit_destructor_for__instance__
0x18006fc30  call    __tlregdtor
0x18006fc35  mov     rbx, [rsp+28h+arg_0]
0x18006fc3a  mov     rax, rdi
0x18006fc3d  add     rsp, 20h
0x18006fc41  pop     rdi
0x18006fc42  retn
```
