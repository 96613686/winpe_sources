# CSsdpCacheEntry::FIsSearchMatchHash(char const *,ulong,_GUID,ulong)

- ea: `0x18001a1b0`
- end: `0x18001a306`
- name: `?FIsSearchMatchHash@CSsdpCacheEntry@@QEAAHPEBDKU_GUID@@K@Z`
- size: `342`
- prototype: `__int64 __usercall@<rax>(CSsdpCacheEntry *__hidden this@<rcx>, const char *Str1@<rdx>, unsigned int@<r8d>, struct _GUID *__struct_ptr@<r9>, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000bdd4`
- `0x180016e2c`

## callees

- `0x18001a1b0`
- `0x18001a30c`
- `0x180037db4`
- `0x180037dcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a217`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a217`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a1d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a1d0`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntry::FIsSearchMatchHash(
        CSsdpCacheEntry *this,
        const char *Str1,
        int a3,
        struct _GUID *a4,
        unsigned int a5)
{
  __int64 v9; // rdx
  unsigned int v10; // edi
  const char *v11; // rax
  const char *v12; // rax
  const char *v14; // r9
  int v15; // ecx
  int v16; // r8d
  unsigned int CachedAddressFamily; // eax
  unsigned int i; // edx
  _QWORD *v19; // r8
  __int64 v20; // rax
  const char *v21; // rbp
  int v22; // edx
  int v23; // ecx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  if ( !strcmp_0(Str1, "ssdp:all") )
    goto LABEL_30;
  v9 = *((_QWORD *)this + 11);
  v10 = 0;
  if ( v9 )
  {
    v11 = *(const char **)(v9 + 8);
    if ( v11 && a5 == *((_DWORD *)this + 65) )
    {
      v14 = (const char *)(Str1 - v11);
      do
      {
        v15 = (unsigned __int8)v14[(_QWORD)v11];
        v16 = *(unsigned __int8 *)v11 - v15;
        if ( v16 )
          break;
        ++v11;
      }
      while ( v15 );
      if ( !v16 )
        goto LABEL_30;
    }
    v12 = *(const char **)(v9 + 24);
    if ( v12 )
    {
      v21 = (const char *)(Str1 - v12);
      do
      {
        v22 = (unsigned __int8)v21[(_QWORD)v12];
        v23 = *(unsigned __int8 *)v12 - v22;
        if ( v23 )
          break;
        ++v12;
      }
      while ( v22 );
      if ( !v23 )
      {
LABEL_30:
        if ( !memcmp_0(a4, &GUID_NULL, 0x10u) )
        {
          CachedAddressFamily = CSsdpCacheEntry::GetCachedAddressFamily(this);
          v10 = 0;
LABEL_13:
          LOBYTE(v10) = (CachedAddressFamily & a3) != 0;
        }
        else
        {
          v10 = 0;
          for ( i = 0; i < *((_DWORD *)this + 26); ++i )
          {
            v19 = (_QWORD *)(*((_QWORD *)this + 12) + ((unsigned __int64)i << 6));
            v20 = *(_QWORD *)&a4->Data1 - v19[6];
            if ( *(_QWORD *)&a4->Data1 == v19[6] )
              v20 = *(_QWORD *)a4->Data4 - v19[7];
            if ( !v20 )
            {
              CachedAddressFamily = (*v19 != 0) | 2;
              if ( !v19[1] )
                CachedAddressFamily = *v19 != 0;
              goto LABEL_13;
            }
          }
        }
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  return v10;
}

```

## disassembly

```asm
0x18001a1b0  push    rbx
0x18001a1b2  push    rbp
0x18001a1b3  push    rsi
0x18001a1b4  push    rdi
0x18001a1b5  push    r14
0x18001a1b7  push    r15
0x18001a1b9  sub     rsp, 28h
0x18001a1bd  mov     rsi, rcx
0x18001a1c0  mov     r15, r9
0x18001a1c3  add     rcx, 0D8h; lpCriticalSection
0x18001a1ca  mov     r14d, r8d
0x18001a1cd  mov     rbp, rdx
0x18001a1d0  call    cs:__imp_EnterCriticalSection
0x18001a1d7  nop     dword ptr [rax+rax+00h]
0x18001a1dc  lea     rdx, aSsdpAll; "ssdp:all"
0x18001a1e3  mov     rcx, rbp; Str1
0x18001a1e6  call    strcmp_0
0x18001a1eb  test    eax, eax
0x18001a1ed  jz      short loc_18001A26A
0x18001a1ef  mov     rdx, [rsi+58h]
0x18001a1f3  xor     edi, edi
0x18001a1f5  test    rdx, rdx
0x18001a1f8  jz      short loc_18001A210
0x18001a1fa  mov     rax, [rdx+8]
0x18001a1fe  test    rax, rax
0x18001a201  jnz     short loc_18001A233
0x18001a203  mov     rax, [rdx+18h]
0x18001a207  test    rax, rax
0x18001a20a  jnz     loc_18001A2CE
0x18001a210  lea     rcx, [rsi+0D8h]; lpCriticalSection
0x18001a217  call    cs:__imp_LeaveCriticalSection
0x18001a21e  nop     dword ptr [rax+rax+00h]
0x18001a223  mov     eax, edi
0x18001a225  add     rsp, 28h
0x18001a229  pop     r15
0x18001a22b  pop     r14
0x18001a22d  pop     rdi
0x18001a22e  pop     rsi
0x18001a22f  pop     rbp
0x18001a230  pop     rbx
0x18001a231  retn
0x18001a233  mov     ecx, [rsi+104h]
0x18001a239  cmp     [rsp+58h+arg_20], ecx
0x18001a240  jnz     short loc_18001A203
0x18001a242  mov     r9, rbp
0x18001a245  sub     r9, rax
0x18001a248  nop     dword ptr [rax+rax+00000000h]
0x18001a250  movzx   r8d, byte ptr [rax]
0x18001a254  movzx   ecx, byte ptr [rax+r9]
0x18001a259  sub     r8d, ecx
0x18001a25c  jnz     short loc_18001A265
0x18001a25e  inc     rax
0x18001a261  test    ecx, ecx
0x18001a263  jnz     short loc_18001A250
0x18001a265  test    r8d, r8d
0x18001a268  jnz     short loc_18001A203
0x18001a26a  mov     r8d, 10h; Size
0x18001a270  lea     rdx, GUID_NULL; Buf2
0x18001a277  mov     rcx, r15; Buf1
0x18001a27a  call    memcmp_0
0x18001a27f  test    eax, eax
0x18001a281  jnz     short loc_18001A29C
0x18001a283  mov     rcx, rsi; this
0x18001a286  call    ?GetCachedAddressFamily@CSsdpCacheEntry@@AEAAKXZ; CSsdpCacheEntry::GetCachedAddressFamily(void)
0x18001a28b  mov     edi, 0
0x18001a290  test    r14d, eax
0x18001a293  setnz   dil
0x18001a297  jmp     loc_18001A210
0x18001a29c  xor     edi, edi
0x18001a29e  xor     edx, edx
0x18001a2a0  cmp     edx, [rsi+68h]
0x18001a2a3  jnb     loc_18001A210
0x18001a2a9  mov     rax, [r15]
0x18001a2ac  mov     r8d, edx
0x18001a2af  shl     r8, 6
0x18001a2b3  add     r8, [rsi+60h]
0x18001a2b7  sub     rax, [r8+30h]
0x18001a2bb  jnz     short loc_18001A2C5
0x18001a2bd  mov     rax, [r15+8]
0x18001a2c1  sub     rax, [r8+38h]
0x18001a2c5  test    rax, rax
0x18001a2c8  jz      short loc_18001A2F0
0x18001a2ca  inc     edx
0x18001a2cc  jmp     short loc_18001A2A0
0x18001a2ce  sub     rbp, rax
0x18001a2d1  movzx   ecx, byte ptr [rax]
0x18001a2d4  movzx   edx, byte ptr [rax+rbp]
0x18001a2d8  sub     ecx, edx
0x18001a2da  jnz     short loc_18001A2E3
0x18001a2dc  inc     rax
0x18001a2df  test    edx, edx
0x18001a2e1  jnz     short loc_18001A2D1
0x18001a2e3  test    ecx, ecx
0x18001a2e5  jnz     loc_18001A210
0x18001a2eb  jmp     loc_18001A26A
0x18001a2f0  xor     ecx, ecx
0x18001a2f2  cmp     [r8], rcx
0x18001a2f5  setnz   cl
0x18001a2f8  mov     eax, ecx
0x18001a2fa  or      eax, 2
0x18001a2fd  cmp     [r8+8], rdi
0x18001a301  cmovz   eax, ecx
0x18001a304  jmp     short loc_18001A290
```
