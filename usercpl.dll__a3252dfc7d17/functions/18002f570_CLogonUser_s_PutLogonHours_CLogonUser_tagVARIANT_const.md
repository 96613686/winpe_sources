# CLogonUser::s_PutLogonHours(CLogonUser *,tagVARIANT const &)

- ea: `0x18002f570`
- end: `0x18002f6d2`
- name: `?s_PutLogonHours@CLogonUser@@CAJPEAV1@AEBUtagVARIANT@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(struct CLogonUser *, const struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002f570`
- `0x18007728a`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002f5cb`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002f5cb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002f640`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002f640`
- `samcli!NetUserSetInfo` at `0x18002f69d`
- `samcli!NetUserSetInfo` at `0x18002f69d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f5ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f662`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f5ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f662`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f6bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f6bd`

## pseudocode

```c
__int64 __fastcall CLogonUser::s_PutLogonHours(const WCHAR *a1, const struct tagVARIANT *a2)
{
  int v4; // ebx
  LONGLONG llVal; // rdi
  unsigned int v6; // ebx
  _BYTE *v7; // r9
  unsigned int i; // edx
  HLOCAL v9; // rax
  signed int v10; // eax
  BYTE buf[8]; // [rsp+30h] [rbp-18h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-10h]
  void *ppvData; // [rsp+88h] [rbp+40h] BYREF

  v4 = -2147024809;
  *(_QWORD *)buf = 0;
  hMem = 0;
  if ( a2->vt != 8203 )
  {
    if ( a2->vt != 11 )
      goto LABEL_20;
    *(_DWORD *)buf = 168;
    v9 = LocalAlloc(0, 0x15u);
    hMem = v9;
    if ( !v9 )
    {
      v4 = -2147024882;
      goto LABEL_20;
    }
    memset_0(v9, (unsigned __int8)-(a2->iVal != 0), 0x15u);
    goto LABEL_17;
  }
  llVal = a2->llVal;
  if ( *(_WORD *)llVal == 1 && !*(_DWORD *)(llVal + 28) )
  {
    ppvData = 0;
    v4 = SafeArrayAccessData((SAFEARRAY *)llVal, &ppvData);
    if ( v4 >= 0 )
    {
      v6 = *(_DWORD *)(llVal + 24);
      *(_DWORD *)buf = v6;
      hMem = LocalAlloc(0x40u, (unsigned __int64)(v6 + 7) >> 3);
      v7 = hMem;
      if ( hMem )
      {
        for ( i = 0; i < v6; ++i )
        {
          if ( *((_WORD *)ppvData + i) )
          {
            v7[(unsigned __int64)i >> 3] |= 1 << (i & 7);
            v7 = hMem;
          }
        }
        v4 = 0;
      }
      else
      {
        v4 = -2147024882;
      }
      SafeArrayUnaccessData((SAFEARRAY *)llVal);
      if ( v4 >= 0 )
      {
LABEL_17:
        v10 = NetUserSetInfo(0, a1 + 6, 0x3FCu, buf, 0);
        v4 = v10;
        if ( v10 > 0 )
          v4 = (unsigned __int16)v10 | 0x80070000;
      }
    }
  }
LABEL_20:
  LocalFree(hMem);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002f570  push    rbp
0x18002f572  push    rbx
0x18002f573  push    rsi
0x18002f574  push    rdi
0x18002f575  push    r14
0x18002f577  push    r15
0x18002f579  mov     rbp, rsp
0x18002f57c  sub     rsp, 48h
0x18002f580  xor     r14d, r14d
0x18002f583  mov     eax, 200Bh
0x18002f588  mov     rdi, rdx
0x18002f58b  mov     rsi, rcx
0x18002f58e  mov     ebx, 80070057h
0x18002f593  mov     qword ptr [rbp+buf], r14
0x18002f597  mov     [rbp+hMem], r14
0x18002f59b  cmp     [rdx], ax
0x18002f59e  jnz     loc_18002F64C
0x18002f5a4  mov     rdi, [rdx+8]
0x18002f5a8  lea     r15d, [r14+1]
0x18002f5ac  cmp     [rdi], r15w
0x18002f5b0  jnz     loc_18002F6B9
0x18002f5b6  cmp     [rdi+1Ch], r14d
0x18002f5ba  jnz     loc_18002F6B9
0x18002f5c0  lea     rdx, [rbp+ppvData]; ppvData
0x18002f5c4  mov     [rbp+ppvData], r14
0x18002f5c8  mov     rcx, rdi; psa
0x18002f5cb  call    cs:__imp_SafeArrayAccessData
0x18002f5d1  mov     ebx, eax
0x18002f5d3  test    eax, eax
0x18002f5d5  js      loc_18002F6B9
0x18002f5db  mov     ebx, [rdi+18h]
0x18002f5de  lea     ecx, [r14+40h]; uFlags
0x18002f5e2  mov     dword ptr [rbp+buf], ebx
0x18002f5e5  lea     edx, [rbx+7]
0x18002f5e8  shr     rdx, 3; uBytes
0x18002f5ec  call    cs:__imp_LocalAlloc
0x18002f5f2  mov     [rbp+hMem], rax
0x18002f5f6  mov     r9, rax
0x18002f5f9  test    rax, rax
0x18002f5fc  jz      short loc_18002F638
0x18002f5fe  mov     edx, r14d
0x18002f601  test    ebx, ebx
0x18002f603  jz      short loc_18002F633
0x18002f605  mov     rcx, [rbp+ppvData]
0x18002f609  mov     r8d, edx
0x18002f60c  cmp     [rcx+r8*2], r14w
0x18002f611  jz      short loc_18002F62C
0x18002f613  shr     r8, 3
0x18002f617  mov     eax, edx
0x18002f619  and     eax, 7
0x18002f61c  movzx   ecx, byte ptr [r8+r9]
0x18002f621  bts     ecx, eax
0x18002f624  mov     [r8+r9], cl
0x18002f628  mov     r9, [rbp+hMem]
0x18002f62c  add     edx, r15d
0x18002f62f  cmp     edx, ebx
0x18002f631  jb      short loc_18002F605
0x18002f633  mov     ebx, r14d
0x18002f636  jmp     short loc_18002F63D
0x18002f638  mov     ebx, 8007000Eh
0x18002f63d  mov     rcx, rdi; psa
0x18002f640  call    cs:__imp_SafeArrayUnaccessData
0x18002f646  test    ebx, ebx
0x18002f648  jns     short loc_18002F688
0x18002f64a  jmp     short loc_18002F6B9
0x18002f64c  cmp     word ptr [rdx], 0Bh
0x18002f650  jnz     short loc_18002F6B9
0x18002f652  mov     ebx, 15h
0x18002f657  mov     dword ptr [rbp+buf], 0A8h
0x18002f65e  mov     edx, ebx; uBytes
0x18002f660  xor     ecx, ecx; uFlags
0x18002f662  call    cs:__imp_LocalAlloc
0x18002f668  mov     [rbp+hMem], rax
0x18002f66c  test    rax, rax
0x18002f66f  jz      short loc_18002F6B4
0x18002f671  movzx   ecx, word ptr [rdi+8]
0x18002f675  mov     r8d, ebx; Size
0x18002f678  neg     cx
0x18002f67b  mov     rcx, rax; void *
0x18002f67e  sbb     edx, edx
0x18002f680  movzx   edx, dl; Val
0x18002f683  call    memset_0
0x18002f688  lea     rdx, [rsi+0Ch]; username
0x18002f68c  mov     [rsp+48h+parm_err], r14; parm_err
0x18002f691  lea     r9, [rbp+buf]; buf
0x18002f695  xor     ecx, ecx; servername
0x18002f697  mov     r8d, 3FCh; level
0x18002f69d  call    cs:__imp_NetUserSetInfo
0x18002f6a3  mov     ebx, eax
0x18002f6a5  test    eax, eax
0x18002f6a7  jle     short loc_18002F6B9
0x18002f6a9  movzx   ebx, ax
0x18002f6ac  or      ebx, 80070000h
0x18002f6b2  jmp     short loc_18002F6B9
0x18002f6b4  mov     ebx, 8007000Eh
0x18002f6b9  mov     rcx, [rbp+hMem]; hMem
0x18002f6bd  call    cs:__imp_LocalFree
0x18002f6c3  mov     eax, ebx
0x18002f6c5  add     rsp, 48h
0x18002f6c9  pop     r15
0x18002f6cb  pop     r14
0x18002f6cd  pop     rdi
0x18002f6ce  pop     rsi
0x18002f6cf  pop     rbx
0x18002f6d0  pop     rbp
0x18002f6d1  retn
```
