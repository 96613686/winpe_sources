# WriteFilesMetadataBuffer(DIRECTORY_SCAN_FUNC_ARGS *)

- ea: `0x18001e310`
- end: `0x18001e421`
- name: `?WriteFilesMetadataBuffer@@YAXPEAUDIRECTORY_SCAN_FUNC_ARGS@@@Z`
- size: `273`
- prototype: `void __fastcall(struct DIRECTORY_SCAN_FUNC_ARGS *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001afb0`

## callees

- `0x1800010b0`
- `0x1800029b4`
- `0x180005c94`
- `0x18001e310`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001e3dc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001e3dc`

## pseudocode

```c
void __fastcall WriteFilesMetadataBuffer(struct DIRECTORY_SCAN_FUNC_ARGS *a1)
{
  int v2; // ecx
  int v3; // r8d
  int v4; // r9d
  void *v5; // rcx
  __int64 v6; // [rsp+50h] [rbp-20h] BYREF
  __int64 v7; // [rsp+58h] [rbp-18h] BYREF
  __int16 v8; // [rsp+60h] [rbp-10h]
  int v9; // [rsp+90h] [rbp+20h] BYREF
  int v10; // [rsp+98h] [rbp+28h] BYREF
  char *v11; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v12; // [rsp+A8h] [rbp+38h] BYREF

  if ( *((_WORD *)a1 + 76) )
  {
    if ( (unsigned int)dword_180040010 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180040010, 0x400000000000LL) )
      {
        v8 = v3;
        v11 = (char *)a1 + 160;
        v7 = *((_QWORD *)a1 + 22);
        v9 = *((unsigned __int16 *)a1 + 77);
        v12 = *((_QWORD *)a1 + 2);
        v10 = *(_DWORD *)a1;
        v6 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperArray<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
          v2,
          (unsigned int)qword_180037370,
          v3,
          v4,
          (__int64)&v6,
          (__int64)&v10,
          (__int64)&v12,
          (__int64)&v9,
          (__int64)&v7,
          (__int64)&v11);
      }
    }
    Sleep(0x28u);
    v5 = (void *)*((_QWORD *)a1 + 22);
    *((_DWORD *)a1 + 38) = 0;
    memset_0(v5, 0, 0x3E80u);
    memset_0(*((void **)a1 + 21), 0, *((unsigned __int16 *)a1 + 81));
    *((_WORD *)a1 + 80) = 0;
  }
}

```

## disassembly

```asm
0x18001e310  push    rbp
0x18001e312  push    rbx
0x18001e313  push    rdi
0x18001e314  mov     rbp, rsp
0x18001e317  sub     rsp, 70h
0x18001e31b  movzx   r8d, word ptr [rcx+98h]
0x18001e323  xor     edi, edi
0x18001e325  mov     rbx, rcx
0x18001e328  test    r8w, r8w
0x18001e32c  jz      loc_18001E419
0x18001e332  mov     eax, cs:dword_180040010
0x18001e338  cmp     eax, 5
0x18001e33b  jbe     loc_18001E3D7
0x18001e341  mov     rdx, 400000000000h
0x18001e34b  lea     rcx, dword_180040010
0x18001e352  call    _tlgKeywordOn
0x18001e357  test    al, al
0x18001e359  jz      short loc_18001E3D7
0x18001e35b  lea     rax, [rbx+0A0h]
0x18001e362  mov     [rbp+var_10], r8w
0x18001e367  mov     [rbp+arg_10], rax
0x18001e36b  lea     rdx, qword_180037370
0x18001e372  mov     rax, [rbx+0B0h]
0x18001e379  mov     [rbp+var_18], rax
0x18001e37d  movzx   eax, word ptr [rbx+9Ah]
0x18001e384  mov     [rbp+arg_0], eax
0x18001e387  mov     rax, [rbx+10h]
0x18001e38b  mov     [rbp+arg_18], rax
0x18001e38f  mov     eax, [rbx]
0x18001e391  mov     [rbp+arg_8], eax
0x18001e394  lea     rax, [rbp+arg_10]
0x18001e398  mov     [rsp+70h+var_28], rax
0x18001e39d  lea     rax, [rbp+var_18]
0x18001e3a1  mov     [rsp+70h+var_30], rax
0x18001e3a6  lea     rax, [rbp+arg_0]
0x18001e3aa  mov     [rsp+70h+var_38], rax
0x18001e3af  lea     rax, [rbp+arg_18]
0x18001e3b3  mov     [rsp+70h+var_40], rax
0x18001e3b8  lea     rax, [rbp+arg_8]
0x18001e3bc  mov     [rsp+70h+var_48], rax
0x18001e3c1  lea     rax, [rbp+var_20]
0x18001e3c5  mov     [rsp+70h+var_50], rax
0x18001e3ca  mov     [rbp+var_20], 1000000h
0x18001e3d2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperArray@$07@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperArray@$07@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperArray<8>,_tlgWrapBuffer<_UNICODE_STRING>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperArray<8> const &,_tlgWrapBuffer<_UNICODE_STRING> const &)
0x18001e3d7  mov     ecx, 28h ; '('; dwMilliseconds
0x18001e3dc  call    cs:__imp_Sleep
0x18001e3e2  mov     rcx, [rbx+0B0h]; void *
0x18001e3e9  xor     edx, edx; Val
0x18001e3eb  mov     r8d, 3E80h; Size
0x18001e3f1  mov     [rbx+98h], edi
0x18001e3f7  call    memset_0
0x18001e3fc  movzx   r8d, word ptr [rbx+0A2h]; Size
0x18001e404  xor     edx, edx; Val
0x18001e406  mov     rcx, [rbx+0A8h]; void *
0x18001e40d  call    memset_0
0x18001e412  mov     [rbx+0A0h], di
0x18001e419  add     rsp, 70h
0x18001e41d  pop     rdi
0x18001e41e  pop     rbx
0x18001e41f  pop     rbp
0x18001e420  retn
```
