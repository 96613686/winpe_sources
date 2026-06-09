# MGetServerConfig

- ea: `0x1800326c0`
- end: `0x1800328fe`
- name: `MGetServerConfig`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180028100`

## callees

- `0x18002c8d4`
- `0x18003144c`
- `0x180031e94`
- `0x180031eec`
- `0x180031fd4`
- `0x1800326c0`

## import_xrefs

- `KERNEL32!GetPrivateProfileSectionW` at `0x1800327c5`
- `KERNEL32!GetPrivateProfileSectionW` at `0x1800327c5`
- `KERNEL32!HeapAlloc` at `0x180032799`
- `KERNEL32!HeapAlloc` at `0x180032799`

## pseudocode

```c
__int64 __fastcall MGetServerConfig(__int64 a1, _DWORD *a2, unsigned int a3, __int64 a4, __int64 a5)
{
  __int64 result; // rax
  __int64 v8; // rbp
  __int64 v9; // r15
  DWORD v10; // edi
  __int16 *v11; // r14
  void *v12; // r13
  unsigned int v13; // edi
  void *v14; // rbp
  __int16 v15; // ax
  __int16 *v16; // rcx
  __int16 *v17; // rdi
  LPVOID lpMem; // [rsp+68h] [rbp+10h] BYREF
  LPVOID v19; // [rsp+78h] [rbp+20h] BYREF

  result = (unsigned int)a2[3];
  lpMem = 0;
  v19 = 0;
  if ( (unsigned int)result > a3 )
  {
    *a2 = -2147483576;
    return result;
  }
  if ( (unsigned int)result < 0x30 )
  {
    *a2 = -2147483571;
    return result;
  }
  *(_DWORD *)a4 = result;
  result = IsNTServer();
  if ( (_DWORD)result )
  {
    result = GetDomainAndUserNames((wchar_t **)&lpMem, (wchar_t **)&v19);
    if ( (_DWORD)result )
    {
      *a2 = result;
      return result;
    }
    v8 = -1;
    v9 = -1;
    v10 = 0;
    v11 = 0;
    do
      ++v9;
    while ( *((_WORD *)lpMem + v9) );
    v12 = v19;
    do
      ++v8;
    while ( *((_WORD *)v19 + v8) );
    do
    {
      if ( v11 )
      {
        ServerFree(v11);
        v10 *= 2;
      }
      else
      {
        v10 = 256;
      }
      v11 = (__int16 *)HeapAlloc(ghTapisrvHeap, 8u, 2 * v10);
      if ( !v11 )
      {
        v14 = lpMem;
        *a2 = -2147483580;
        goto LABEL_37;
      }
      *v11 = 0;
    }
    while ( GetPrivateProfileSectionW(gszTapiAdministrators, (LPWSTR)v11, v10, gszFileName) >= v10 - 2 );
    v13 = 2 * v10 + 2 * (v9 + v8 + 2);
    *(_QWORD *)(a4 + 16) = 0;
    *(_QWORD *)(a4 + 24) = 0;
    *(_QWORD *)(a4 + 32) = 0;
    *(_QWORD *)(a4 + 40) = 0;
    *(_DWORD *)(a4 + 12) = 1;
    if ( (unsigned int)IsSharingEnabled() )
      *(_DWORD *)(a4 + 12) |= 2u;
    *(_DWORD *)(a4 + 8) = 48;
    v14 = lpMem;
    if ( *(_DWORD *)a4 >= v13 )
    {
      InsertString(a4, a4 + 16, lpMem);
      InsertString(a4, a4 + 24, v12);
      v15 = *v11;
      v16 = v11;
      while ( v15 )
      {
        v17 = v16;
        while ( v15 && v15 != 61 && v15 != 32 )
          v15 = *++v17;
        if ( *v17 )
        {
          *v17 = 0;
          InsertString(a4, a4 + 40, v16);
          do
            ++v17;
          while ( *v17 );
        }
        v16 = v17 + 1;
        v15 = v17[1];
      }
      if ( *(_DWORD *)(a4 + 40) )
        InsertString(a4, a4 + 40, &gszEmptyString);
      v13 = *(_DWORD *)(a4 + 8);
    }
    *(_DWORD *)(a4 + 4) = v13;
    ServerFree(v11);
LABEL_37:
    ServerFree(v14);
    result = ServerFree(v12);
  }
  else
  {
    *(_DWORD *)(a4 + 8) = 48;
    *(_DWORD *)(a4 + 4) = 48;
  }
  if ( !*a2 )
  {
    result = a5;
    a2[3] = 0;
    *(_DWORD *)result = *(_DWORD *)(a4 + 8) + 60;
  }
  return result;
}

```

## disassembly

```asm
0x1800326c0  mov     [rsp+arg_0], rbx
0x1800326c5  push    rbp
0x1800326c6  push    rsi
0x1800326c7  push    rdi
0x1800326c8  push    r12
0x1800326ca  push    r13
0x1800326cc  push    r14
0x1800326ce  push    r15
0x1800326d0  sub     rsp, 20h
0x1800326d4  mov     eax, [rdx+0Ch]
0x1800326d7  xor     r12d, r12d
0x1800326da  mov     [rsp+58h+lpMem], r12
0x1800326df  mov     rbx, r9
0x1800326e2  mov     [rsp+58h+arg_18], r12
0x1800326e7  mov     rsi, rdx
0x1800326ea  cmp     eax, r8d
0x1800326ed  jbe     short loc_1800326FA
0x1800326ef  mov     dword ptr [rdx], 80000048h
0x1800326f5  jmp     loc_1800328E9
0x1800326fa  mov     edi, 30h ; '0'
0x1800326ff  cmp     eax, edi
0x180032701  jnb     short loc_18003270E
0x180032703  mov     dword ptr [rdx], 8000004Dh
0x180032709  jmp     loc_1800328E9
0x18003270e  mov     [r9], eax
0x180032711  call    IsNTServer
0x180032716  test    eax, eax
0x180032718  jnz     short loc_180032725
0x18003271a  mov     [rbx+8], edi
0x18003271d  mov     [rbx+4], edi
0x180032720  jmp     loc_1800328D0
0x180032725  lea     rdx, [rsp+58h+arg_18]
0x18003272a  lea     rcx, [rsp+58h+lpMem]
0x18003272f  call    GetDomainAndUserNames
0x180032734  test    eax, eax
0x180032736  jz      short loc_18003273F
0x180032738  mov     [rsi], eax
0x18003273a  jmp     loc_1800328E9
0x18003273f  mov     rax, [rsp+58h+lpMem]
0x180032744  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180032748  mov     [rsp+58h+lpMem], rax
0x18003274d  mov     r15, rbp
0x180032750  mov     edi, r12d
0x180032753  mov     r14, r12
0x180032756  inc     r15
0x180032759  cmp     [rax+r15*2], r12w
0x18003275e  jnz     short loc_180032756
0x180032760  mov     r13, [rsp+58h+arg_18]
0x180032765  inc     rbp
0x180032768  cmp     [r13+rbp*2+0], r12w
0x18003276e  jnz     short loc_180032765
0x180032770  test    r14, r14
0x180032773  jz      short loc_180032781
0x180032775  mov     rcx, r14; lpMem
0x180032778  call    ServerFree
0x18003277d  add     edi, edi
0x18003277f  jmp     short loc_180032786
0x180032781  mov     edi, 100h
0x180032786  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18003278d  lea     r12d, [rdi+rdi]
0x180032791  mov     r8d, r12d; dwBytes
0x180032794  mov     edx, 8; dwFlags
0x180032799  call    cs:__imp_HeapAlloc
0x18003279f  mov     r14, rax
0x1800327a2  test    rax, rax
0x1800327a5  jz      loc_1800328B2
0x1800327ab  xor     eax, eax
0x1800327ad  lea     r9, gszFileName; "..\\TAPI\\tsec.ini"
0x1800327b4  mov     r8d, edi; nSize
0x1800327b7  mov     [r14], ax
0x1800327bb  mov     rdx, r14; lpReturnedString
0x1800327be  lea     rcx, gszTapiAdministrators; "TapiAdministrators"
0x1800327c5  call    cs:__imp_GetPrivateProfileSectionW
0x1800327cb  lea     ecx, [rdi-2]
0x1800327ce  cmp     eax, ecx
0x1800327d0  jnb     short loc_180032770
0x1800327d2  lea     eax, [rbp+2]
0x1800327d5  add     eax, r15d
0x1800327d8  lea     edi, [r12+rax*2]
0x1800327dc  xor     r12d, r12d
0x1800327df  mov     [rbx+10h], r12
0x1800327e3  mov     [rbx+18h], r12
0x1800327e7  mov     [rbx+20h], r12
0x1800327eb  mov     [rbx+28h], r12
0x1800327ef  mov     dword ptr [rbx+0Ch], 1
0x1800327f6  call    IsSharingEnabled
0x1800327fb  test    eax, eax
0x1800327fd  jz      short loc_180032803
0x1800327ff  or      dword ptr [rbx+0Ch], 2
0x180032803  mov     dword ptr [rbx+8], 30h ; '0'
0x18003280a  mov     rbp, [rsp+58h+lpMem]
0x18003280f  cmp     [rbx], edi
0x180032811  jb      loc_1800328A5
0x180032817  lea     rdx, [rbx+10h]
0x18003281b  mov     r8, rbp
0x18003281e  mov     rcx, rbx
0x180032821  call    InsertString
0x180032826  lea     rdx, [rbx+18h]
0x18003282a  mov     r8, r13
0x18003282d  mov     rcx, rbx
0x180032830  call    InsertString
0x180032835  movzx   eax, word ptr [r14]
0x180032839  mov     rcx, r14
0x18003283c  jmp     short loc_180032885
0x18003283e  mov     rdi, rcx
0x180032841  jmp     short loc_180032856
0x180032843  cmp     ax, 3Dh ; '='
0x180032847  jz      short loc_18003285B
0x180032849  cmp     ax, 20h ; ' '
0x18003284d  jz      short loc_18003285B
0x18003284f  add     rdi, 2
0x180032853  movzx   eax, word ptr [rdi]
0x180032856  test    ax, ax
0x180032859  jnz     short loc_180032843
0x18003285b  cmp     [rdi], r12w
0x18003285f  jz      short loc_18003287E
0x180032861  mov     r8, rcx
0x180032864  mov     [rdi], r12w
0x180032868  mov     rcx, rbx
0x18003286b  lea     rdx, [rbx+28h]
0x18003286f  call    InsertString
0x180032874  add     rdi, 2
0x180032878  cmp     [rdi], r12w
0x18003287c  jnz     short loc_180032874
0x18003287e  lea     rcx, [rdi+2]
0x180032882  movzx   eax, word ptr [rcx]
0x180032885  test    ax, ax
0x180032888  jnz     short loc_18003283E
0x18003288a  lea     rdx, [rbx+28h]
0x18003288e  cmp     [rdx], r12d
0x180032891  jz      short loc_1800328A2
0x180032893  lea     r8, gszEmptyString
0x18003289a  mov     rcx, rbx
0x18003289d  call    InsertString
0x1800328a2  mov     edi, [rbx+8]
0x1800328a5  mov     rcx, r14; lpMem
0x1800328a8  mov     [rbx+4], edi
0x1800328ab  call    ServerFree
0x1800328b0  jmp     short loc_1800328C0
0x1800328b2  mov     rbp, [rsp+58h+lpMem]
0x1800328b7  xor     r12d, r12d
0x1800328ba  mov     dword ptr [rsi], 80000044h
0x1800328c0  mov     rcx, rbp; lpMem
0x1800328c3  call    ServerFree
0x1800328c8  mov     rcx, r13; lpMem
0x1800328cb  call    ServerFree
0x1800328d0  cmp     [rsi], r12d
0x1800328d3  jnz     short loc_1800328E9
0x1800328d5  mov     rax, [rsp+58h+arg_20]
0x1800328dd  mov     [rsi+0Ch], r12d
0x1800328e1  mov     ecx, [rbx+8]
0x1800328e4  add     ecx, 3Ch ; '<'
0x1800328e7  mov     [rax], ecx
0x1800328e9  mov     rbx, [rsp+58h+arg_0]
0x1800328ee  add     rsp, 20h
0x1800328f2  pop     r15
0x1800328f4  pop     r14
0x1800328f6  pop     r13
0x1800328f8  pop     r12
0x1800328fa  pop     rdi
0x1800328fb  pop     rsi
0x1800328fc  pop     rbp
0x1800328fd  retn
```
