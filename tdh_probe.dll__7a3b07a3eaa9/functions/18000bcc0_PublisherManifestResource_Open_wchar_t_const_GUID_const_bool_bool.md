# PublisherManifestResource::Open(wchar_t const *,_GUID const *,bool,bool)

- ea: `0x18000bcc0`
- end: `0x18000bf65`
- name: `?Open@PublisherManifestResource@@QEAAKPEB_WPEBU_GUID@@_N2@Z`
- size: `677`
- prototype: `unsigned int __fastcall(PublisherManifestResource *this, const wchar_t *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task`

## callers

- `0x18000cb50`

## callees

- `0x180007b20`
- `0x18000b360`
- `0x18000bcc0`
- `0x18000c6cc`
- `0x18000d030`
- `0x18000d200`
- `0x180017c9c`
- `0x180017d08`
- `0x18002bcbc`
- `0x18002bd28`
- `0x18002bd94`
- `0x18002be00`
- `0x18002be6c`
- `0x18002bed8`

## string_xrefs

- `0x18000bcd7`: `WEVT_TEMPLATE`

## pseudocode

```c
unsigned int __fastcall PublisherManifestResource::Open(
        PublisherManifestResource *this,
        const wchar_t *a2,
        const struct _GUID *a3)
{
  ResourceHolder *v3; // rsi
  unsigned int result; // eax
  struct _GUID v7; // xmm0
  __int64 v8; // rax
  int *v9; // rdi
  unsigned int v10; // r14d
  unsigned int i; // ebp
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  unsigned int v18; // edx
  ResourceHolder *v19; // rcx
  _DWORD *v20; // r10
  char inited; // al
  unsigned int v22; // edx
  ResourceHolder *v23; // rcx
  _DWORD *v24; // r10
  unsigned int v25; // eax
  __int64 v26; // r10
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  unsigned int v32; // r8d
  __int64 v33; // r10
  bool v34; // [rsp+28h] [rbp-30h]

  v3 = (PublisherManifestResource *)((char *)this + 120);
  result = ResourceHolder::Open((PublisherManifestResource *)((char *)this + 120), a2, L"#1", L"WEVT_TEMPLATE", a3, v34);
  if ( !result )
  {
    v7 = *a3;
    v8 = *((_QWORD *)this + 16);
    v9 = (int *)(*((_QWORD *)this + 17) + 16LL);
    *(struct _GUID *)((char *)this + 104) = v7;
    v10 = *(_DWORD *)(v8 + 8);
    for ( i = 0; ; ++i )
    {
      if ( i >= *(_DWORD *)(*((_QWORD *)this + 17) + 12LL) )
        return 0;
      v12 = *v9;
      if ( *v9 <= 7 )
        break;
      v27 = v12 - 8;
      if ( v27 )
      {
        v28 = v27 - 1;
        if ( v28 )
        {
          v29 = v28 - 1;
          if ( !v29 )
            goto LABEL_17;
          v30 = v29 - 1;
          if ( v30 )
          {
            v31 = v30 - 1;
            if ( v31 )
            {
              if ( v31 == 1 )
              {
                inited = InitTablePointer_ProvAttribsTable_((char *)this + 96, v3, v9);
                goto LABEL_16;
              }
LABEL_45:
              inited = v10 > 0x10005;
              goto LABEL_16;
            }
            inited = InitTablePointer_EventAttribsTable_((char *)this + 88, v3, v9);
          }
          else
          {
            inited = InitTablePointer_EventFlagsTable_((char *)this + 40, v3, v9);
          }
        }
        else
        {
          inited = InitTablePointer_FilterTable_((char *)this + 80, v3, v9);
        }
      }
      else
      {
        inited = InitTablePointer_NamedQueryTable_((char *)this + 72, v3, v9);
      }
LABEL_16:
      if ( !inited )
        return 13;
LABEL_17:
      v9 += 2;
    }
    if ( v12 == 7 )
    {
      inited = InitTablePointer_TemplateTable_((char *)this + 64, v3, v9);
      goto LABEL_16;
    }
    if ( !v12 )
    {
      inited = InitTablePointer_LevelTable_(this, v3, v9);
      goto LABEL_16;
    }
    v13 = v12 - 1;
    if ( !v13 )
    {
      inited = InitTablePointer_TaskTable_((char *)this + 8, v3, v9);
      goto LABEL_16;
    }
    v14 = v13 - 1;
    if ( !v14 )
    {
      if ( *((_QWORD *)this + 2)
        || !ResourceHolder::ValidateBytes(v3, v9[1], 0xCu)
        || (v24 = (_DWORD *)(*(_QWORD *)v3 + v22), *v24 != 1329811535)
        || (v25 = v24[2], v25 > 0x15555554)
        || !ResourceHolder::ValidateBytes(v23, v22, 12 * (v25 + 1)) )
      {
LABEL_15:
        inited = 0;
        goto LABEL_16;
      }
      *((_QWORD *)this + 2) = v26;
      goto LABEL_24;
    }
    v15 = v14 - 1;
    if ( !v15 )
    {
      inited = InitTablePointer_KeywordTable_((char *)this + 24, v3, v9);
      goto LABEL_16;
    }
    v16 = v15 - 1;
    if ( !v16 )
    {
      inited = InitTablePointer_EventTable_((char *)this + 32, v3, v9);
      goto LABEL_16;
    }
    v17 = v16 - 1;
    if ( !v17 )
    {
      if ( *((_QWORD *)this + 6) )
        goto LABEL_15;
      if ( !ResourceHolder::ValidateBytes(v3, v9[1], 0xCu) )
        goto LABEL_15;
      v20 = (_DWORD *)(*(_QWORD *)v3 + v18);
      if ( *v20 != 1312901187 )
        goto LABEL_15;
      v32 = v20[2];
      if ( v32 > 0xFFFFFFF || !ResourceHolder::ValidateBytes(v19, v18, 16 * v32 + 12) )
        goto LABEL_15;
      *((_QWORD *)this + 6) = v33;
LABEL_24:
      inited = 1;
      goto LABEL_16;
    }
    if ( v17 == 1 )
    {
      inited = InitTablePointer_MapTable_((char *)this + 56, v3, v9);
      goto LABEL_16;
    }
    goto LABEL_45;
  }
  return result;
}

```

## disassembly

```asm
0x18000bcc0  push    rbx
0x18000bcc2  push    rbp
0x18000bcc3  push    rsi
0x18000bcc4  push    rdi
0x18000bcc5  push    r14
0x18000bcc7  sub     rsp, 30h
0x18000bccb  lea     rsi, [rcx+78h]
0x18000bccf  mov     [rsp+58h+var_38], r8; struct _GUID *
0x18000bcd4  mov     rdi, r8
0x18000bcd7  lea     r9, aWevtTemplate; "WEVT_TEMPLATE"
0x18000bcde  mov     rbx, rcx
0x18000bce1  lea     r8, a1; "#1"
0x18000bce8  mov     rcx, rsi; this
0x18000bceb  call    ?Open@ResourceHolder@@QEAAKPEB_W00PEBU_GUID@@_N@Z; ResourceHolder::Open(wchar_t const *,wchar_t const *,wchar_t const *,_GUID const *,bool)
0x18000bcf0  test    eax, eax
0x18000bcf2  jnz     loc_18000BE45
0x18000bcf8  movups  xmm0, xmmword ptr [rdi]
0x18000bcfb  mov     rax, [rbx+80h]
0x18000bd02  mov     rdi, [rbx+88h]
0x18000bd09  add     rdi, 10h
0x18000bd0d  movdqu  xmmword ptr [rbx+68h], xmm0
0x18000bd12  mov     r14d, [rax+8]
0x18000bd16  xor     ebp, ebp
0x18000bd18  mov     rax, [rbx+88h]
0x18000bd1f  cmp     ebp, [rax+0Ch]
0x18000bd22  jnb     loc_18000BE43
0x18000bd28  mov     ecx, [rdi]
0x18000bd2a  cmp     ecx, 7
0x18000bd2d  jg      loc_18000BDFD
0x18000bd33  jz      loc_18000BE50
0x18000bd39  test    ecx, ecx
0x18000bd3b  jz      loc_18000BEF3
0x18000bd41  sub     ecx, 1
0x18000bd44  jz      loc_18000BEDF
0x18000bd4a  sub     ecx, 1
0x18000bd4d  jz      short loc_18000BDAC
0x18000bd4f  sub     ecx, 1
0x18000bd52  jz      loc_18000BECB
0x18000bd58  sub     ecx, 1
0x18000bd5b  jz      loc_18000BEB7
0x18000bd61  sub     ecx, 1
0x18000bd64  jnz     loc_18000BE6B
0x18000bd6a  cmp     qword ptr [rbx+30h], 0
0x18000bd6f  jnz     short loc_18000BD97
0x18000bd71  mov     edx, [rdi+4]; unsigned int
0x18000bd74  lea     r8d, [rcx+0Ch]; unsigned int
0x18000bd78  mov     rcx, rsi; this
0x18000bd7b  call    ?ValidateBytes@ResourceHolder@@AEBA_NKK@Z; ResourceHolder::ValidateBytes(ulong,ulong)
0x18000bd80  test    al, al
0x18000bd82  jz      short loc_18000BD97
0x18000bd84  mov     r10d, edx
0x18000bd87  add     r10, [rsi]
0x18000bd8a  cmp     dword ptr [r10], 4E414843h
0x18000bd91  jz      loc_18000BE88
0x18000bd97  xor     al, al
0x18000bd99  test    al, al
0x18000bd9b  jz      loc_18000BE64
0x18000bda1  inc     ebp
0x18000bda3  add     rdi, 8
0x18000bda7  jmp     loc_18000BD18
0x18000bdac  cmp     qword ptr [rbx+10h], 0
0x18000bdb1  jnz     short loc_18000BD97
0x18000bdb3  mov     edx, [rdi+4]; unsigned int
0x18000bdb6  mov     r8d, 0Ch; unsigned int
0x18000bdbc  mov     rcx, rsi; this
0x18000bdbf  call    ?ValidateBytes@ResourceHolder@@AEBA_NKK@Z; ResourceHolder::ValidateBytes(ulong,ulong)
0x18000bdc4  test    al, al
0x18000bdc6  jz      short loc_18000BD97
0x18000bdc8  mov     r10d, edx
0x18000bdcb  add     r10, [rsi]
0x18000bdce  cmp     dword ptr [r10], 4F43504Fh
0x18000bdd5  jnz     short loc_18000BD97
0x18000bdd7  mov     eax, [r10+8]
0x18000bddb  cmp     eax, 15555554h
0x18000bde0  ja      short loc_18000BD97
0x18000bde2  inc     eax
0x18000bde4  lea     r8d, [rax+rax*2]
0x18000bde8  shl     r8d, 2; unsigned int
0x18000bdec  call    ?ValidateBytes@ResourceHolder@@AEBA_NKK@Z; ResourceHolder::ValidateBytes(ulong,ulong)
0x18000bdf1  test    al, al
0x18000bdf3  jz      short loc_18000BD97
0x18000bdf5  mov     [rbx+10h], r10
0x18000bdf9  mov     al, 1
0x18000bdfb  jmp     short loc_18000BD99
0x18000bdfd  sub     ecx, 8
0x18000be00  jz      loc_18000BF51
0x18000be06  sub     ecx, 1
0x18000be09  jz      loc_18000BF3D
0x18000be0f  sub     ecx, 1
0x18000be12  jz      short loc_18000BDA1
0x18000be14  sub     ecx, 1
0x18000be17  jz      loc_18000BF29
0x18000be1d  sub     ecx, 1
0x18000be20  jz      loc_18000BF15
0x18000be26  cmp     ecx, 1
0x18000be29  jnz     loc_18000BF06
0x18000be2f  lea     rcx, [rbx+60h]
0x18000be33  mov     r8, rdi
0x18000be36  mov     rdx, rsi
0x18000be39  call    InitTablePointer_ProvAttribsTable_
0x18000be3e  jmp     loc_18000BD99
0x18000be43  xor     eax, eax
0x18000be45  add     rsp, 30h
0x18000be49  pop     r14
0x18000be4b  pop     rdi
0x18000be4c  pop     rsi
0x18000be4d  pop     rbp
0x18000be4e  pop     rbx
0x18000be4f  retn
0x18000be50  lea     rcx, [rbx+40h]
0x18000be54  mov     r8, rdi
0x18000be57  mov     rdx, rsi
0x18000be5a  call    InitTablePointer_TemplateTable_
0x18000be5f  jmp     loc_18000BD99
0x18000be64  mov     eax, 0Dh
0x18000be69  jmp     short loc_18000BE45
0x18000be6b  cmp     ecx, 1
0x18000be6e  jnz     loc_18000BF06
0x18000be74  lea     rcx, [rbx+38h]
0x18000be78  mov     r8, rdi
0x18000be7b  mov     rdx, rsi
0x18000be7e  call    InitTablePointer_MapTable_
0x18000be83  jmp     loc_18000BD99
0x18000be88  mov     r8d, [r10+8]
0x18000be8c  cmp     r8d, 0FFFFFFFh
0x18000be93  ja      loc_18000BD97
0x18000be99  shl     r8d, 4
0x18000be9d  add     r8d, 0Ch; unsigned int
0x18000bea1  call    ?ValidateBytes@ResourceHolder@@AEBA_NKK@Z; ResourceHolder::ValidateBytes(ulong,ulong)
0x18000bea6  test    al, al
0x18000bea8  jz      loc_18000BD97
0x18000beae  mov     [rbx+30h], r10
0x18000beb2  jmp     loc_18000BDF9
0x18000beb7  lea     rcx, [rbx+20h]
0x18000bebb  mov     r8, rdi
0x18000bebe  mov     rdx, rsi
0x18000bec1  call    InitTablePointer_EventTable_
0x18000bec6  jmp     loc_18000BD99
0x18000becb  lea     rcx, [rbx+18h]
0x18000becf  mov     r8, rdi
0x18000bed2  mov     rdx, rsi
0x18000bed5  call    InitTablePointer_KeywordTable_
0x18000beda  jmp     loc_18000BD99
0x18000bedf  lea     rcx, [rbx+8]
0x18000bee3  mov     r8, rdi
0x18000bee6  mov     rdx, rsi
0x18000bee9  call    InitTablePointer_TaskTable_
0x18000beee  jmp     loc_18000BD99
0x18000bef3  mov     r8, rdi
0x18000bef6  mov     rdx, rsi
0x18000bef9  mov     rcx, rbx
0x18000befc  call    InitTablePointer_LevelTable_
0x18000bf01  jmp     loc_18000BD99
0x18000bf06  cmp     r14d, 10005h
0x18000bf0d  setnbe  al
0x18000bf10  jmp     loc_18000BD99
0x18000bf15  lea     rcx, [rbx+58h]
0x18000bf19  mov     r8, rdi
0x18000bf1c  mov     rdx, rsi
0x18000bf1f  call    InitTablePointer_EventAttribsTable_
0x18000bf24  jmp     loc_18000BD99
0x18000bf29  lea     rcx, [rbx+28h]
0x18000bf2d  mov     r8, rdi
0x18000bf30  mov     rdx, rsi
0x18000bf33  call    InitTablePointer_EventFlagsTable_
0x18000bf38  jmp     loc_18000BD99
0x18000bf3d  lea     rcx, [rbx+50h]
0x18000bf41  mov     r8, rdi
0x18000bf44  mov     rdx, rsi
0x18000bf47  call    InitTablePointer_FilterTable_
0x18000bf4c  jmp     loc_18000BD99
0x18000bf51  lea     rcx, [rbx+48h]
0x18000bf55  mov     r8, rdi
0x18000bf58  mov     rdx, rsi
0x18000bf5b  call    InitTablePointer_NamedQueryTable_
0x18000bf60  jmp     loc_18000BD99
```
