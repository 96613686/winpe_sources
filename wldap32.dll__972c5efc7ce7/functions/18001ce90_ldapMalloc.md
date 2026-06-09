# ldapMalloc

- ea: `0x18001ce90`
- end: `0x18001cf6a`
- name: `ldapMalloc`
- size: `218`
- prototype: ``
- caller_count: `82`
- callee_count: `2`
- tags: ``

## callers

- `0x1800018d0`
- `0x1800022c0`
- `0x180003840`
- `0x180004740`
- `0x180005170`
- `0x1800057a0`
- `0x180006510`
- `0x1800094a0`
- `0x18000a358`
- `0x18000bbf0`
- `0x18000da50`
- `0x18000e0d0`
- `0x18001611c`
- `0x1800164a0`
- `0x180017854`
- `0x18001b0d4`
- `0x18001ba9c`
- `0x18001c2d0`
- `0x18001de00`
- `0x18001e800`
- `0x18001ea90`
- `0x18001f96c`
- `0x180020228`
- `0x180020990`
- `0x18002227c`
- `0x1800227d8`
- `0x180022fe4`
- `0x1800230a0`
- `0x1800245ec`
- `0x180026b50`
- `0x180027580`
- `0x180028a60`
- `0x18002ae10`
- `0x18002b5fc`
- `0x18002b800`
- `0x18002ca68`
- `0x18002cd4c`
- `0x18002d1a8`
- `0x18002d7f0`
- `0x18002df60`
- `0x18002e6d4`
- `0x180030df0`
- `0x180031128`
- `0x1800314a8`
- `0x180031c98`
- `0x180032968`
- `0x1800334bc`
- `0x180038678`
- `0x18003a274`
- `0x18003ae3c`

## callees

- `0x1800037a8`
- `0x18001ce90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ceb3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ceb3`

## pseudocode

```c
_DWORD *__fastcall ldapMalloc(unsigned int a1, int a2)
{
  unsigned int v2; // esi
  _DWORD *v5; // rbx
  int v6; // ecx
  unsigned int v7; // eax

  v2 = a1 + 8;
  if ( a1 + 8 < a1 )
  {
    v5 = 0;
    v2 = -1;
  }
  else
  {
    v5 = HeapAlloc(LdapHeap, 8u, v2);
  }
  v6 = g_fTracingOn;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
  {
    LDAPClientPrint(8, "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n", v2, (_DWORD)v5, a2);
    v6 = g_fTracingOn;
  }
  v7 = LdapAllocatedHeap;
  if ( v5 )
  {
    *v5 = a2;
    v5[1] = a1;
    v5 += 2;
    v7 += a1;
    LdapAllocatedHeap = v7;
  }
  if ( v6 && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
    LDAPClientPrint(8, "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n", a1, (_DWORD)v5, a2, v7);
  return v5;
}

```

## disassembly

```asm
0x18001ce90  push    rbx
0x18001ce92  push    rbp
0x18001ce93  push    rsi
0x18001ce94  push    rdi
0x18001ce95  sub     rsp, 38h
0x18001ce99  lea     esi, [rcx+8]
0x18001ce9c  mov     ebp, edx
0x18001ce9e  mov     edi, ecx
0x18001cea0  cmp     esi, ecx
0x18001cea2  jb      short loc_18001CEF9
0x18001cea4  mov     rcx, cs:LdapHeap; hHeap
0x18001ceab  mov     edx, 8; dwFlags
0x18001ceb0  mov     r8d, esi; dwBytes
0x18001ceb3  call    cs:__imp_HeapAlloc
0x18001ceba  nop     dword ptr [rax+rax+00h]
0x18001cebf  mov     rbx, rax
0x18001cec2  mov     ecx, cs:g_fTracingOn
0x18001cec8  test    ecx, ecx
0x18001ceca  jnz     short loc_18001CF02
0x18001cecc  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x18001ced2  test    rbx, rbx
0x18001ced5  jz      short loc_18001CEE8
0x18001ced7  mov     [rbx], ebp
0x18001ced9  mov     [rbx+4], edi
0x18001cedc  add     rbx, 8
0x18001cee0  add     eax, edi
0x18001cee2  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x18001cee8  test    ecx, ecx
0x18001ceea  jnz     short loc_18001CF37
0x18001ceec  mov     rax, rbx
0x18001ceef  add     rsp, 38h
0x18001cef3  pop     rdi
0x18001cef4  pop     rsi
0x18001cef5  pop     rbp
0x18001cef6  pop     rbx
0x18001cef7  retn
0x18001cef9  xor     ebx, ebx
0x18001cefb  mov     esi, 0FFFFFFFFh
0x18001cf00  jmp     short loc_18001CEC2
0x18001cf02  cmp     cs:g_fProviderEnabled, 0
0x18001cf09  jz      short loc_18001CECC
0x18001cf0b  test    byte ptr cs:g_ulTraceFlags, 8
0x18001cf12  jz      short loc_18001CECC
0x18001cf14  mov     r9, rbx
0x18001cf17  mov     [rsp+58h+var_38], ebp
0x18001cf1b  mov     r8d, esi
0x18001cf1e  lea     rdx, aLdapmallocAllo; "ldapMalloc allocated 0x%x bytes at addr"...
0x18001cf25  mov     ecx, 8
0x18001cf2a  call    LDAPClientPrint
0x18001cf2f  mov     ecx, cs:g_fTracingOn
0x18001cf35  jmp     short loc_18001CECC
0x18001cf37  cmp     cs:g_fProviderEnabled, 0
0x18001cf3e  jz      short loc_18001CEEC
0x18001cf40  test    byte ptr cs:g_ulTraceFlags, 8
0x18001cf47  jz      short loc_18001CEEC
0x18001cf49  mov     [rsp+58h+var_30], eax
0x18001cf4d  lea     rdx, aLdapmalloc0x08; "ldapMalloc 0x%08x bytes at address 0x%x"...
0x18001cf54  mov     r9, rbx
0x18001cf57  mov     [rsp+58h+var_38], ebp
0x18001cf5b  mov     r8d, edi
0x18001cf5e  mov     ecx, 8
0x18001cf63  call    LDAPClientPrint
0x18001cf68  jmp     short loc_18001CEEC
```
