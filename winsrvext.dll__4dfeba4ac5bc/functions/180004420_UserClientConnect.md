# UserClientConnect

- ea: `0x180004420`
- end: `0x1800044c0`
- name: `UserClientConnect`
- size: `160`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180004420`

## import_xrefs

- `CSRSRV!CsrQueryApiPort` at `0x180004442`
- `CSRSRV!CsrQueryApiPort` at `0x180004442`
- `win32u!NtUserProcessConnect` at `0x1800044a3`
- `win32u!NtUserProcessConnect` at `0x1800044a3`
- `win32u!gDispatchTableValues` at `0x18000448c`
- `win32u!NtUserSetInformationThread` at `0x18000446d`
- `win32u!NtUserSetInformationThread` at `0x18000446d`

## pseudocode

```c
__int64 __fastcall UserClientConnect(__int64 a1, _DWORD *a2, _DWORD *a3)
{
  __int64 result; // rax

  if ( CsrApiPort
    || (CsrApiPort = CsrQueryApiPort(), result = NtUserSetInformationThread(-2, 10, &CsrApiPort), (int)result >= 0) )
  {
    if ( *a3 == 584 )
    {
      *a2 = gDispatchTableValues;
      return NtUserProcessConnect(*(_QWORD *)(a1 + 80), 576, a2);
    }
    else
    {
      return 3221225485LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004420  mov     [rsp+arg_0], rbx
0x180004425  mov     [rsp+arg_8], rsi
0x18000442a  push    rdi
0x18000442b  sub     rsp, 20h
0x18000442f  cmp     cs:CsrApiPort, 0
0x180004437  mov     rbx, r8
0x18000443a  mov     rdi, rdx
0x18000443d  mov     rsi, rcx
0x180004440  jnz     short loc_18000447D
0x180004442  call    cs:__imp_CsrQueryApiPort
0x180004449  nop     dword ptr [rax+rax+00h]
0x18000444e  mov     r9d, 8
0x180004454  lea     r8, CsrApiPort
0x18000445b  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x180004462  mov     cs:CsrApiPort, rax
0x180004469  lea     edx, [r9+2]
0x18000446d  call    cs:__imp_NtUserSetInformationThread
0x180004474  nop     dword ptr [rax+rax+00h]
0x180004479  test    eax, eax
0x18000447b  js      short loc_1800044AF
0x18000447d  cmp     dword ptr [rbx], 248h
0x180004483  jz      short loc_18000448C
0x180004485  mov     eax, 0C000000Dh
0x18000448a  jmp     short loc_1800044AF
0x18000448c  mov     rax, cs:__imp_gDispatchTableValues
0x180004493  mov     r8, rdi
0x180004496  mov     edx, 240h
0x18000449b  mov     ecx, [rax]
0x18000449d  mov     [rdi], ecx
0x18000449f  mov     rcx, [rsi+50h]
0x1800044a3  call    cs:__imp_NtUserProcessConnect
0x1800044aa  nop     dword ptr [rax+rax+00h]
0x1800044af  mov     rbx, [rsp+28h+arg_0]
0x1800044b4  mov     rsi, [rsp+28h+arg_8]
0x1800044b9  add     rsp, 20h
0x1800044bd  pop     rdi
0x1800044be  retn
```
