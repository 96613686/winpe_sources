# CLdapBer::~CLdapBer(void)

- ea: `0x180014600`
- end: `0x1800147e7`
- name: `??1CLdapBer@@QEAA@XZ`
- size: `487`
- prototype: `void __fastcall(CLdapBer *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180012ab0`
- `0x180014460`
- `0x1800164a0`
- `0x1800491d4`

## callees

- `0x1800037a8`
- `0x180014600`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800146a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800146a5`

## string_xrefs

- `0x180014754`: `Freeing memory at 0x%x which is already freed\n`

## pseudocode

```c
void __fastcall CLdapBer::~CLdapBer(CLdapBer *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int v4; // r9d
  int v5; // r8d
  int v6; // eax
  HANDLE v7; // rcx

  v1 = *((_QWORD *)this + 2);
  *((_DWORD *)this + 1) = 0;
  *(_QWORD *)((char *)this + 836) = 0;
  *((_DWORD *)this + 8) = 0;
  if ( !v1 || *((_BYTE *)this + 856) )
  {
    *((_QWORD *)this + 2) = 0;
    *((_DWORD *)this + 2) = 0;
    return;
  }
  v3 = *(_DWORD *)(v1 - 8);
  if ( v3 == 1684095564 )
  {
    *((_QWORD *)this + 2) = 0;
    *((_DWORD *)this + 2) = 0;
    return;
  }
  if ( v3 != 1701987916 )
    goto LABEL_5;
  if ( g_fTracingOn )
  {
    if ( g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(8, "Freeing memory at 0x%x which is already freed\n", v1);
LABEL_5:
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(
        8,
        "ldapfree freed       0x%x bytes at address 0x%x of tag 0x%x.\n",
        *(_DWORD *)(v1 - 4),
        v1 - 8,
        1919238732);
  }
  v4 = *(_DWORD *)(v1 - 8);
  if ( v4 != 1919238732 && g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
    LDAPClientPrint(8, "Expected tag 0x%x but found tag 0x%x\n", 1919238732, v4);
  v5 = *(_DWORD *)(v1 - 4);
  v6 = LdapAllocatedHeap - v5;
  LdapAllocatedHeap -= v5;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
    LDAPClientPrint(8, "ldapFree   0x%08x bytes at address 0x%x of tag %x, tot=%d.\n", v5, v1, 1919238732, v6);
  v7 = LdapHeap;
  *(_DWORD *)(v1 - 8) = 1701987916;
  HeapFree(v7, 0, (LPVOID)(v1 - 8));
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x180014600  mov     [rsp+arg_8], rbx
0x180014605  mov     [rsp+arg_10], rbp
0x18001460a  push    rdi
0x18001460b  sub     rsp, 30h
0x18001460f  mov     rdi, [rcx+10h]
0x180014613  xor     ebp, ebp
0x180014615  mov     [rcx+4], ebp
0x180014618  mov     rbx, rcx
0x18001461b  mov     [rcx+344h], rbp
0x180014622  mov     [rcx+20h], ebp
0x180014625  test    rdi, rdi
0x180014628  jz      loc_1800146CE
0x18001462e  cmp     [rcx+358h], bpl
0x180014635  jnz     loc_1800146CE
0x18001463b  mov     eax, [rdi-8]
0x18001463e  mov     [rsp+38h+arg_0], rsi
0x180014643  cmp     eax, 6461424Ch
0x180014648  jz      loc_180014723
0x18001464e  cmp     eax, 6572464Ch
0x180014653  jz      loc_18001472C
0x180014659  cmp     cs:g_fTracingOn, ebp
0x18001465f  jnz     loc_18001476A
0x180014665  mov     r9d, [rdi-8]
0x180014669  cmp     r9d, 7265424Ch
0x180014670  jnz     short loc_1800146E6
0x180014672  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x180014678  mov     r8d, [rdi-4]
0x18001467c  sub     eax, r8d
0x18001467f  cmp     cs:g_fTracingOn, ebp
0x180014685  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x18001468b  jnz     loc_1800147A9
0x180014691  mov     rcx, cs:LdapHeap; hHeap
0x180014698  lea     r8, [rdi-8]; lpMem
0x18001469c  xor     edx, edx; dwFlags
0x18001469e  mov     dword ptr [rdi-8], 6572464Ch
0x1800146a5  call    cs:__imp_HeapFree
0x1800146ac  nop     dword ptr [rax+rax+00h]
0x1800146b1  mov     [rbx+10h], rbp
0x1800146b5  mov     [rbx+8], ebp
0x1800146b8  mov     rsi, [rsp+38h+arg_0]
0x1800146bd  mov     rbx, [rsp+38h+arg_8]
0x1800146c2  mov     rbp, [rsp+38h+arg_10]
0x1800146c7  add     rsp, 30h
0x1800146cb  pop     rdi
0x1800146cc  retn
0x1800146ce  mov     rbx, [rsp+38h+arg_8]
0x1800146d3  mov     [rcx+10h], rbp
0x1800146d7  mov     [rcx+8], ebp
0x1800146da  mov     rbp, [rsp+38h+arg_10]
0x1800146df  add     rsp, 30h
0x1800146e3  pop     rdi
0x1800146e4  retn
0x1800146e6  cmp     cs:g_fTracingOn, ebp
0x1800146ec  jz      short loc_180014672
0x1800146ee  cmp     cs:g_fProviderEnabled, ebp
0x1800146f4  jz      loc_180014672
0x1800146fa  test    byte ptr cs:g_ulTraceFlags, 8
0x180014701  jz      loc_180014672
0x180014707  mov     r8d, 7265424Ch
0x18001470d  lea     rdx, aExpectedTag0xX; "Expected tag 0x%x but found tag 0x%x\n"
0x180014714  mov     ecx, 8
0x180014719  call    LDAPClientPrint
0x18001471e  jmp     loc_180014672
0x180014723  mov     [rcx+10h], rbp
0x180014727  mov     [rcx+8], ebp
0x18001472a  jmp     short loc_1800146B8
0x18001472c  cmp     cs:g_fTracingOn, ebp
0x180014732  jz      loc_180014665
0x180014738  cmp     cs:g_fProviderEnabled, ebp
0x18001473e  jz      loc_180014659
0x180014744  test    byte ptr cs:g_ulTraceFlags, 8
0x18001474b  jz      loc_180014659
0x180014751  mov     r8, rdi
0x180014754  lea     rdx, aFreeingMemoryA; "Freeing memory at 0x%x which is already"...
0x18001475b  mov     ecx, 8
0x180014760  call    LDAPClientPrint
0x180014765  jmp     loc_180014659
0x18001476a  cmp     cs:g_fProviderEnabled, ebp
0x180014770  jz      loc_180014665
0x180014776  test    byte ptr cs:g_ulTraceFlags, 8
0x18001477d  jz      loc_180014665
0x180014783  mov     r8d, [rdi-4]
0x180014787  lea     r9, [rdi-8]
0x18001478b  lea     rdx, aLdapfreeFreed0; "ldapfree freed       0x%x bytes at addr"...
0x180014792  mov     [rsp+38h+var_18], 7265424Ch
0x18001479a  mov     ecx, 8
0x18001479f  call    LDAPClientPrint
0x1800147a4  jmp     loc_180014665
0x1800147a9  cmp     cs:g_fProviderEnabled, ebp
0x1800147af  jz      loc_180014691
0x1800147b5  test    byte ptr cs:g_ulTraceFlags, 8
0x1800147bc  jz      loc_180014691
0x1800147c2  mov     [rsp+38h+var_10], eax
0x1800147c6  lea     rdx, aLdapfree0x08xB; "ldapFree   0x%08x bytes at address 0x%x"...
0x1800147cd  mov     r9, rdi
0x1800147d0  mov     [rsp+38h+var_18], 7265424Ch
0x1800147d8  mov     ecx, 8
0x1800147dd  call    LDAPClientPrint
0x1800147e2  jmp     loc_180014691
```
