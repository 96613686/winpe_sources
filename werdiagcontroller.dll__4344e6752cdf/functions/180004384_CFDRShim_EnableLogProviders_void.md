# CFDRShim::EnableLogProviders(void)

- ea: `0x180004384`
- end: `0x18000440c`
- name: `?EnableLogProviders@CFDRShim@@QEAAJXZ`
- size: `136`
- prototype: `__int64 __fastcall(CFDRShim *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800040b4`
- `0x180004420`

## callees

- `0x180004384`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x1800043ec`
- `ntdll!DbgPrintEx` at `0x1800043ec`
- `api-ms-win-eventing-legacy-l1-1-0!EnableTrace` at `0x1800043c6`
- `api-ms-win-eventing-legacy-l1-1-0!EnableTrace` at `0x1800043c6`

## pseudocode

```c
__int64 __fastcall CFDRShim::EnableLogProviders(CFDRShim *this)
{
  int v1; // esi
  unsigned int i; // edi
  __int64 v4; // rbp
  ULONG v5; // eax

  v1 = 0;
  for ( i = 0; i < *(_DWORD *)this; ++i )
  {
    v4 = 28LL * i;
    if ( !*(_DWORD *)((char *)this + v4 + 32) )
    {
      v5 = EnableTrace(
             1u,
             *(_DWORD *)((char *)this + v4 + 28),
             *(_DWORD *)((char *)this + v4 + 24),
             (LPCGUID)((char *)this + v4 + 8),
             *((_QWORD *)this + 36));
      *(_DWORD *)((char *)this + v4 + 32) = v5 == 0;
      if ( v5 )
      {
        DbgPrintEx(0x96u, 0, "WERDIAG: Failed enabling trace provider. Win32 error: %08X\n", v5);
        ++v1;
      }
    }
  }
  return v1 != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x180004384  push    rbx
0x180004386  push    rbp
0x180004387  push    rsi
0x180004388  push    rdi
0x180004389  sub     rsp, 38h
0x18000438d  xor     esi, esi
0x18000438f  xor     edi, edi
0x180004391  mov     rbx, rcx
0x180004394  cmp     [rcx], esi
0x180004396  jbe     short loc_1800043FA
0x180004398  mov     eax, edi
0x18000439a  imul    rbp, rax, 1Ch
0x18000439e  cmp     dword ptr [rbx+rbp+20h], 0
0x1800043a3  jnz     short loc_1800043F4
0x1800043a5  mov     rax, [rbx+120h]
0x1800043ac  lea     r9, [rbx+8]
0x1800043b0  mov     r8d, [rbx+rbp+18h]; EnableLevel
0x1800043b5  add     r9, rbp; ControlGuid
0x1800043b8  mov     edx, [rbx+rbp+1Ch]; EnableFlag
0x1800043bc  mov     ecx, 1; Enable
0x1800043c1  mov     [rsp+58h+TraceHandle], rax; TraceHandle
0x1800043c6  call    cs:__imp_EnableTrace
0x1800043cc  xor     ecx, ecx
0x1800043ce  test    eax, eax
0x1800043d0  setz    cl
0x1800043d3  mov     [rbx+rbp+20h], ecx
0x1800043d7  test    eax, eax
0x1800043d9  jz      short loc_1800043F4
0x1800043db  mov     r9d, eax
0x1800043de  lea     r8, aWerdiagFailedE_3; "WERDIAG: Failed enabling trace provider"...
0x1800043e5  xor     edx, edx; Level
0x1800043e7  mov     ecx, 96h; ComponentId
0x1800043ec  call    cs:__imp_DbgPrintEx
0x1800043f2  inc     esi
0x1800043f4  inc     edi
0x1800043f6  cmp     edi, [rbx]
0x1800043f8  jb      short loc_180004398
0x1800043fa  neg     esi
0x1800043fc  sbb     eax, eax
0x1800043fe  and     eax, 80004005h
0x180004403  add     rsp, 38h
0x180004407  pop     rdi
0x180004408  pop     rsi
0x180004409  pop     rbp
0x18000440a  pop     rbx
0x18000440b  retn
```
