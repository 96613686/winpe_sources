# CTls13ClientHandshake::GenerateBinderEntries(_Tls13OfferedPsk *,unsigned __int64)

- ea: `0x180045a44`
- end: `0x180045d3e`
- name: `?GenerateBinderEntries@CTls13ClientHandshake@@AEAAKPEAU_Tls13OfferedPsk@@_K@Z`
- size: `762`
- prototype: `unsigned int __fastcall(CTls13ClientHandshake *__hidden this, struct _Tls13OfferedPsk *, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18004d548`

## callees

- `0x18000ad58`
- `0x180021da8`
- `0x180045a44`
- `0x180045d44`
- `0x180045dc4`
- `0x18004d0cc`
- `0x1800597b0`
- `0x18005a160`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045d08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045d08`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180045aa2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180045aa2`
- `ncrypt!SslDuplicateTranscriptHash` at `0x180045b0c`
- `ncrypt!SslDuplicateTranscriptHash` at `0x180045b0c`
- `ncrypt!SslCreateHandshakeHash` at `0x180045b2b`
- `ncrypt!SslCreateHandshakeHash` at `0x180045b2b`
- `ncrypt!SslFreeObject` at `0x180045cf7`
- `ncrypt!SslFreeObject` at `0x180045cf7`

## pseudocode

```c
__int64 __fastcall CTls13ClientHandshake::GenerateBinderEntries(
        CTlsRecord **this,
        struct _Tls13OfferedPsk *a2,
        unsigned __int64 a3)
{
  unsigned __int64 v6; // rbx
  CCipherMill *v7; // rcx
  _QWORD *v8; // r14
  unsigned int BinderData; // ebx
  unsigned __int64 v10; // rdi
  __int16 v11; // cx
  unsigned __int16 v12; // dx
  CTlsRecord *v13; // rcx
  __int64 v14; // rax
  unsigned int HandshakeHash; // eax
  __int64 v16; // rdx
  unsigned __int64 i; // rdi
  unsigned __int16 v18; // r12
  CTlsRecord *v19; // rcx
  unsigned __int64 j; // rdi
  __int64 v21; // rcx
  _WORD v23[2]; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int16 v24; // [rsp+44h] [rbp-35h] BYREF
  unsigned __int64 AProvider; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int8 v26[64]; // [rsp+50h] [rbp-29h] BYREF

  if ( !a3 || !a2 )
    return 87;
  AProvider = CCipherMill::GetAProvider((CCipherMill *)this);
  v6 = AProvider;
  v8 = LocalAlloc(0x40u, 8 * a3);
  if ( v8 )
  {
    v10 = 0;
    v23[0] = 0;
    v11 = 0;
    v12 = *((_WORD *)this[1] + 17);
    v24 = v12;
    while ( v10 < a3 )
    {
      v13 = this[1];
      if ( *((_DWORD *)v13 + 23) == 100 )
      {
        v14 = (*(__int64 (__fastcall **)(CTlsRecord *, _QWORD))(*(_QWORD *)v13 + 576LL))(v13, 0);
        HandshakeHash = SslDuplicateTranscriptHash(v6, v14, &v8[v10], 0);
      }
      else
      {
        HandshakeHash = SslCreateHandshakeHash(v6, &v8[v10], v12, *((unsigned int *)a2 + 10 * v10 + 7), 0);
      }
      BinderData = HandshakeHash;
      if ( HandshakeHash )
        goto LABEL_29;
      BinderData = CTlsRecord::HashPskBinderTranscript(this[3], AProvider, v8[v10]);
      if ( BinderData )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v16 = 29;
LABEL_16:
          WPP_SF_d(*((_QWORD *)v7 + 2), v16, WPP_ca7b144d2da03908b1ea89985908c21d_Traceguids, BinderData);
        }
        goto LABEL_29;
      }
      v6 = AProvider;
      v12 = v24;
      v11 = *((_WORD *)a2 + 20 * v10 + 12) + 1 + v23[0];
      v23[0] = v11;
      ++v10;
    }
    v23[0] = __ROR2__(v11, 8);
    BinderData = (*(__int64 (__fastcall **)(CTlsRecord *, __int64, _WORD *))(*(_QWORD *)this[3] + 32LL))(
                   this[3],
                   2,
                   v23);
    if ( !BinderData )
    {
      memset_0(v26, 0, sizeof(v26));
      for ( i = 0; i < a3; ++i )
      {
        v18 = *((_WORD *)a2 + 20 * i + 12);
        if ( v18 > 0x40u )
        {
          BinderData = 1359;
          break;
        }
        BinderData = CTls13Context::GenerateBinderData(
                       v7,
                       AProvider,
                       *((_QWORD *)a2 + 5 * i + 4),
                       v8[i],
                       *((_BYTE *)a2 + 40 * i),
                       v26,
                       *((unsigned __int16 *)a2 + 20 * i + 12));
        if ( BinderData )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v16 = 30;
            goto LABEL_16;
          }
          break;
        }
        v19 = this[3];
        LOBYTE(v24) = v18;
        BinderData = (*(__int64 (__fastcall **)(CTlsRecord *, __int64, unsigned __int16 *))(*(_QWORD *)v19 + 32LL))(
                       v19,
                       1,
                       &v24);
        if ( BinderData )
          break;
        BinderData = (*(__int64 (__fastcall **)(CTlsRecord *, _QWORD, unsigned __int8 *))(*(_QWORD *)this[3] + 32LL))(
                       this[3],
                       v18,
                       v26);
        if ( BinderData )
          break;
      }
    }
  }
  else
  {
    BinderData = 14;
  }
LABEL_29:
  if ( AProvider )
    CCipherMill::DeferenceProvider(v7, &AProvider);
  if ( v8 )
  {
    for ( j = 0; j < a3; ++j )
    {
      v21 = v8[j];
      if ( v21 )
        SslFreeObject(v21, 0);
    }
    LocalFree(v8);
  }
  return BinderData;
}

```

## disassembly

```asm
0x180045a44  mov     [rsp-8+arg_18], rbx
0x180045a49  push    rbp
0x180045a4a  push    rsi
0x180045a4b  push    rdi
0x180045a4c  push    r12
0x180045a4e  push    r13
0x180045a50  push    r14
0x180045a52  push    r15
0x180045a54  lea     rbp, [rsp-27h]
0x180045a59  sub     rsp, 0A0h
0x180045a60  mov     rax, cs:__security_cookie
0x180045a67  xor     rax, rsp
0x180045a6a  mov     [rbp+57h+var_40], rax
0x180045a6e  mov     rsi, r8
0x180045a71  mov     r15, rdx
0x180045a74  mov     r13, rcx
0x180045a77  test    r8, r8
0x180045a7a  jz      loc_180045D12
0x180045a80  test    rdx, rdx
0x180045a83  jz      loc_180045D12
0x180045a89  call    ?GetAProvider@CCipherMill@@QEAA_KXZ; CCipherMill::GetAProvider(void)
0x180045a8e  lea     rdx, ds:0[rsi*8]; uBytes
0x180045a96  mov     [rbp+57h+var_88], rax
0x180045a9a  mov     ecx, 40h ; '@'; uFlags
0x180045a9f  mov     rbx, rax
0x180045aa2  call    cs:__imp_LocalAlloc
0x180045aa8  mov     r14, rax
0x180045aab  mov     r12d, 1
0x180045ab1  test    rax, rax
0x180045ab4  jnz     short loc_180045ABE
0x180045ab6  lea     ebx, [rax+0Eh]
0x180045ab9  jmp     loc_180045CD0
0x180045abe  xor     eax, eax
0x180045ac0  xor     edi, edi
0x180045ac2  mov     [rbp+57h+var_90], ax
0x180045ac6  xor     ecx, ecx
0x180045ac8  mov     rax, [r13+8]
0x180045acc  movzx   edx, word ptr [rax+22h]
0x180045ad0  mov     [rbp+57h+var_8C], dx
0x180045ad4  cmp     rdi, rsi
0x180045ad7  jnb     loc_180045BC3
0x180045add  mov     rcx, [r13+8]
0x180045ae1  lea     rax, [rdi+rdi*4]
0x180045ae5  lea     r12, [r14+rdi*8]
0x180045ae9  cmp     dword ptr [rcx+5Ch], 64h ; 'd'
0x180045aed  jnz     short loc_180045B14
0x180045aef  mov     rax, [rcx]
0x180045af2  xor     edx, edx
0x180045af4  mov     rax, [rax+240h]
0x180045afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b00  xor     r9d, r9d
0x180045b03  mov     r8, r12
0x180045b06  mov     rdx, rax
0x180045b09  mov     rcx, rbx
0x180045b0c  call    cs:__imp_SslDuplicateTranscriptHash
0x180045b12  jmp     short loc_180045B31
0x180045b14  mov     r9d, [r15+rax*8+1Ch]
0x180045b19  mov     rcx, rbx
0x180045b1c  movzx   r8d, dx
0x180045b20  mov     rdx, r12
0x180045b23  mov     dword ptr [rsp+0D0h+var_B0], 0
0x180045b2b  call    cs:__imp_SslCreateHandshakeHash
0x180045b31  mov     ebx, eax
0x180045b33  test    eax, eax
0x180045b35  jnz     loc_180045CCA
0x180045b3b  mov     r8, [r12]; unsigned __int64
0x180045b3f  mov     rdx, [rbp+57h+var_88]; unsigned __int64
0x180045b43  mov     rcx, [r13+18h]; this
0x180045b47  call    ?HashPskBinderTranscript@CTlsRecord@@QEAAK_K0@Z; CTlsRecord::HashPskBinderTranscript(unsigned __int64,unsigned __int64)
0x180045b4c  mov     ebx, eax
0x180045b4e  test    eax, eax
0x180045b50  jnz     short loc_180045B7F
0x180045b52  movzx   ecx, [rbp+57h+var_90]
0x180045b56  lea     r12d, [rbx+1]
0x180045b5a  mov     rbx, [rbp+57h+var_88]
0x180045b5e  lea     rax, [rdi+rdi*4]
0x180045b62  movzx   eax, word ptr [r15+rax*8+18h]
0x180045b68  movzx   edx, [rbp+57h+var_8C]
0x180045b6c  add     ax, r12w
0x180045b70  add     cx, ax
0x180045b73  mov     [rbp+57h+var_90], cx
0x180045b77  add     rdi, r12
0x180045b7a  jmp     loc_180045AD4
0x180045b7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180045b86  lea     rax, WPP_GLOBAL_Control
0x180045b8d  mov     r12d, 1
0x180045b93  cmp     rcx, rax
0x180045b96  jz      loc_180045CD0
0x180045b9c  test    [rcx+1Ch], r12b
0x180045ba0  jz      loc_180045CD0
0x180045ba6  lea     edx, [r12+1Ch]
0x180045bab  mov     rcx, [rcx+10h]
0x180045baf  lea     r8, WPP_ca7b144d2da03908b1ea89985908c21d_Traceguids
0x180045bb6  mov     r9d, ebx
0x180045bb9  call    WPP_SF_d
0x180045bbe  jmp     loc_180045CD0
0x180045bc3  ror     cx, 8
0x180045bc7  lea     r8, [rbp+57h+var_90]
0x180045bcb  mov     [rbp+57h+var_90], cx
0x180045bcf  mov     edx, 2
0x180045bd4  mov     rcx, [r13+18h]
0x180045bd8  mov     rax, [rcx]
0x180045bdb  mov     rax, [rax+20h]
0x180045bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045be4  mov     ebx, eax
0x180045be6  test    eax, eax
0x180045be8  jnz     loc_180045CD0
0x180045bee  xor     edx, edx; Val
0x180045bf0  lea     r8d, [rax+40h]; Size
0x180045bf4  lea     rcx, [rbp+57h+var_80]; void *
0x180045bf8  call    memset_0
0x180045bfd  xor     edi, edi
0x180045bff  cmp     rdi, rsi
0x180045c02  jnb     loc_180045CD0
0x180045c08  lea     r8, [rdi+rdi*4]
0x180045c0c  mov     eax, 40h ; '@'
0x180045c11  movzx   r12d, word ptr [r15+r8*8+18h]
0x180045c17  cmp     r12w, ax
0x180045c1b  ja      loc_180045CC5
0x180045c21  mov     r9, [r14+rdi*8]; unsigned __int64
0x180045c25  lea     rax, [rbp+57h+var_80]
0x180045c29  mov     rdx, [rbp+57h+var_88]; unsigned __int64
0x180045c2d  mov     [rsp+0D0h+var_A0], r12d; unsigned int
0x180045c32  mov     [rsp+0D0h+var_A8], rax; unsigned __int8 *
0x180045c37  mov     al, [r15+r8*8]
0x180045c3b  mov     r8, [r15+r8*8+20h]; unsigned __int64
0x180045c40  mov     [rsp+0D0h+var_B0], al; char
0x180045c44  call    ?GenerateBinderData@CTls13Context@@QEAAK_K00EPEAEK@Z; CTls13Context::GenerateBinderData(unsigned __int64,unsigned __int64,unsigned __int64,uchar,uchar *,ulong)
0x180045c49  mov     ebx, eax
0x180045c4b  test    eax, eax
0x180045c4d  jnz     short loc_180045C9C
0x180045c4f  mov     rcx, [r13+18h]
0x180045c53  lea     edx, [rbx+1]
0x180045c56  mov     byte ptr [rbp+57h+var_8C], r12b
0x180045c5a  lea     r8, [rbp+57h+var_8C]
0x180045c5e  mov     rax, [rcx]
0x180045c61  mov     rax, [rax+20h]
0x180045c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c6a  mov     ebx, eax
0x180045c6c  test    eax, eax
0x180045c6e  jnz     short loc_180045CCA
0x180045c70  mov     rcx, [r13+18h]
0x180045c74  lea     r8, [rbp+57h+var_80]
0x180045c78  movzx   edx, r12w
0x180045c7c  mov     rax, [rcx]
0x180045c7f  mov     rax, [rax+20h]
0x180045c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c88  mov     ebx, eax
0x180045c8a  mov     r12d, 1
0x180045c90  test    eax, eax
0x180045c92  jnz     short loc_180045CD0
0x180045c94  add     rdi, r12
0x180045c97  jmp     loc_180045BFF
0x180045c9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180045ca3  lea     rax, WPP_GLOBAL_Control
0x180045caa  mov     r12d, 1
0x180045cb0  cmp     rcx, rax
0x180045cb3  jz      short loc_180045CD0
0x180045cb5  test    [rcx+1Ch], r12b
0x180045cb9  jz      short loc_180045CD0
0x180045cbb  lea     edx, [r12+1Dh]
0x180045cc0  jmp     loc_180045BAB
0x180045cc5  mov     ebx, 54Fh
0x180045cca  mov     r12d, 1
0x180045cd0  cmp     [rbp+57h+var_88], 0
0x180045cd5  jz      short loc_180045CE0
0x180045cd7  lea     rdx, [rbp+57h+var_88]; unsigned __int64 *
0x180045cdb  call    ?DeferenceProvider@CCipherMill@@QEAAXPEA_K@Z; CCipherMill::DeferenceProvider(unsigned __int64 *)
0x180045ce0  test    r14, r14
0x180045ce3  jz      short loc_180045D0E
0x180045ce5  xor     edi, edi
0x180045ce7  test    rsi, rsi
0x180045cea  jz      short loc_180045D05
0x180045cec  mov     rcx, [r14+rdi*8]
0x180045cf0  test    rcx, rcx
0x180045cf3  jz      short loc_180045CFD
0x180045cf5  xor     edx, edx
0x180045cf7  call    cs:__imp_SslFreeObject
0x180045cfd  add     rdi, r12
0x180045d00  cmp     rdi, rsi
0x180045d03  jb      short loc_180045CEC
0x180045d05  mov     rcx, r14; hMem
0x180045d08  call    cs:__imp_LocalFree
0x180045d0e  mov     eax, ebx
0x180045d10  jmp     short loc_180045D17
0x180045d12  mov     eax, 57h ; 'W'
0x180045d17  mov     rcx, [rbp+57h+var_40]
0x180045d1b  xor     rcx, rsp; StackCookie
0x180045d1e  call    __security_check_cookie
0x180045d23  mov     rbx, [rsp+0D0h+arg_18]
0x180045d2b  add     rsp, 0A0h
0x180045d32  pop     r15
0x180045d34  pop     r14
0x180045d36  pop     r13
0x180045d38  pop     r12
0x180045d3a  pop     rdi
0x180045d3b  pop     rsi
0x180045d3c  pop     rbp
0x180045d3d  retn
```
