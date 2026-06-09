# CCipherMill::GetPrivateKeyFromProvider(_CERT_CONTEXT const *,ProviderToPrivateKey * *,ulong *)

- ea: `0x18004819c`
- end: `0x1800482f3`
- name: `?GetPrivateKeyFromProvider@CCipherMill@@QEAAKPEBU_CERT_CONTEXT@@PEAPEAUProviderToPrivateKey@@PEAK@Z`
- size: `343`
- prototype: `unsigned int __fastcall(CCipherMill *__hidden this, const struct _CERT_CONTEXT *, struct ProviderToPrivateKey **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18004800c`

## callees

- `0x18000a5f4`
- `0x180021eb0`
- `0x18004819c`
- `0x1800597b0`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800482a7`
- `ntdll!RtlReleaseResource` at `0x1800482a7`
- `ntdll!RtlAcquireResourceShared` at `0x1800481e1`
- `ntdll!RtlAcquireResourceShared` at `0x1800481e1`
- `ncrypt!SslOpenPrivateKey` at `0x180048216`
- `ncrypt!SslOpenPrivateKey` at `0x180048216`
- `ncrypt!SslFreeObject` at `0x1800482bc`
- `ncrypt!SslFreeObject` at `0x1800482bc`

## pseudocode

```c
__int64 __fastcall CCipherMill::GetPrivateKeyFromProvider(
        CCipherMill *this,
        const struct _CERT_CONTEXT *a2,
        struct ProviderToPrivateKey **a3,
        unsigned int *a4)
{
  unsigned int *v5; // r13
  unsigned int v7; // ebp
  __int64 v8; // rsi
  CCipherMill *v9; // rcx
  struct ProviderToPrivateKey *v10; // r14
  __int64 v11; // r15
  unsigned __int64 *v12; // rbx
  unsigned __int64 v13; // rax
  _QWORD v16[32]; // [rsp+30h] [rbp-148h] BYREF

  v5 = a4;
  v7 = 1168;
  RtlAcquireResourceShared(&Resource, 1u);
  v8 = 0;
  if ( qword_1800AE498 )
  {
    while ( 1 )
    {
      v7 = SslOpenPrivateKey(*(_QWORD *)&g_cCipherMill[8 * v8 + 128], &v16[v8], a2, 64);
      if ( v7 )
        break;
      v8 = (unsigned int)(v8 + 1);
      if ( (unsigned int)v8 >= qword_1800AE498 )
      {
        v10 = (struct ProviderToPrivateKey *)SPExternalAlloc(16 * qword_1800AE498);
        if ( v10 )
        {
          v11 = 0;
          if ( qword_1800AE498 )
          {
            do
            {
              v12 = (unsigned __int64 *)((char *)v10 + 16 * (unsigned int)v11);
              CCipherMill::ReferenceProvider(v9, *(_QWORD *)&g_cCipherMill[8 * v11 + 128], v12);
              v13 = v16[v11];
              v11 = (unsigned int)(v11 + 1);
              v12[1] = v13;
            }
            while ( (unsigned int)v11 < qword_1800AE498 );
            v5 = a4;
          }
          *a3 = v10;
          *v5 = qword_1800AE498;
        }
        else
        {
          v7 = 14;
        }
        break;
      }
    }
  }
  RtlReleaseResource(&Resource);
  if ( v7 )
  {
    while ( (_DWORD)v8 )
    {
      v8 = (unsigned int)(v8 - 1);
      SslFreeObject(v16[v8], 0);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18004819c  mov     [rsp+arg_0], rbx
0x1800481a1  push    rbp
0x1800481a2  push    rsi
0x1800481a3  push    rdi
0x1800481a4  push    r12
0x1800481a6  push    r13
0x1800481a8  push    r14
0x1800481aa  push    r15
0x1800481ac  sub     rsp, 140h
0x1800481b3  mov     rax, cs:__security_cookie
0x1800481ba  xor     rax, rsp
0x1800481bd  mov     [rsp+178h+var_48], rax
0x1800481c5  mov     rbx, rdx
0x1800481c8  mov     [rsp+178h+var_158], r9
0x1800481cd  mov     dl, 1; Wait
0x1800481cf  lea     rcx, Resource; Resource
0x1800481d6  mov     r13, r9
0x1800481d9  mov     r12, r8
0x1800481dc  mov     ebp, 490h
0x1800481e1  call    cs:__imp_RtlAcquireResourceShared
0x1800481e7  xor     esi, esi
0x1800481e9  cmp     dword ptr cs:qword_1800AE498, esi
0x1800481ef  jbe     loc_1800482A0
0x1800481f5  lea     rax, ?g_cCipherMill@@3VCCipherMill@@A; CCipherMill g_cCipherMill
0x1800481fc  mov     rcx, [rax+rsi*8+80h]
0x180048204  lea     rdx, [rsp+178h+var_148]
0x180048209  lea     rdx, [rdx+rsi*8]
0x18004820d  mov     r9d, 40h ; '@'
0x180048213  mov     r8, rbx
0x180048216  call    cs:__imp_SslOpenPrivateKey
0x18004821c  mov     ebp, eax
0x18004821e  test    eax, eax
0x180048220  jnz     short loc_1800482A0
0x180048222  mov     rcx, cs:qword_1800AE498
0x180048229  lea     rax, ?g_cCipherMill@@3VCCipherMill@@A; CCipherMill g_cCipherMill
0x180048230  inc     esi
0x180048232  cmp     esi, ecx
0x180048234  jb      short loc_1800481FC
0x180048236  shl     ecx, 4; uBytes
0x180048239  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x18004823e  mov     r14, rax
0x180048241  test    rax, rax
0x180048244  jnz     short loc_18004824B
0x180048246  lea     ebp, [rax+0Eh]
0x180048249  jmp     short loc_1800482A0
0x18004824b  xor     r15d, r15d
0x18004824e  cmp     dword ptr cs:qword_1800AE498, r15d
0x180048255  jbe     short loc_180048292
0x180048257  lea     r13, ?g_cCipherMill@@3VCCipherMill@@A; CCipherMill g_cCipherMill
0x18004825e  mov     rdx, [r13+r15*8+80h]; unsigned __int64
0x180048266  mov     ebx, r15d
0x180048269  shl     rbx, 4
0x18004826d  add     rbx, r14
0x180048270  mov     r8, rbx; unsigned __int64 *
0x180048273  call    ?ReferenceProvider@CCipherMill@@QEAAX_KPEA_K@Z; CCipherMill::ReferenceProvider(unsigned __int64,unsigned __int64 *)
0x180048278  mov     rax, [rsp+r15*8+178h+var_148]
0x18004827d  inc     r15d
0x180048280  mov     [rbx+8], rax
0x180048284  cmp     r15d, dword ptr cs:qword_1800AE498
0x18004828b  jb      short loc_18004825E
0x18004828d  mov     r13, [rsp+178h+var_158]
0x180048292  mov     [r12], r14
0x180048296  mov     eax, dword ptr cs:qword_1800AE498
0x18004829c  mov     [r13+0], eax
0x1800482a0  lea     rcx, Resource; Resource
0x1800482a7  call    cs:__imp_RtlReleaseResource
0x1800482ad  test    ebp, ebp
0x1800482af  jnz     short loc_1800482C2
0x1800482b1  jmp     short loc_1800482C6
0x1800482b3  dec     esi
0x1800482b5  xor     edx, edx
0x1800482b7  mov     rcx, [rsp+rsi*8+178h+var_148]
0x1800482bc  call    cs:__imp_SslFreeObject
0x1800482c2  test    esi, esi
0x1800482c4  jnz     short loc_1800482B3
0x1800482c6  mov     eax, ebp
0x1800482c8  mov     rcx, [rsp+178h+var_48]
0x1800482d0  xor     rcx, rsp; StackCookie
0x1800482d3  call    __security_check_cookie
0x1800482d8  mov     rbx, [rsp+178h+arg_0]
0x1800482e0  add     rsp, 140h
0x1800482e7  pop     r15
0x1800482e9  pop     r14
0x1800482eb  pop     r13
0x1800482ed  pop     r12
0x1800482ef  pop     rdi
0x1800482f0  pop     rsi
0x1800482f1  pop     rbp
0x1800482f2  retn
```
