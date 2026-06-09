# WriteInstallersHashBuffer(DIRECTORY_SCAN_FUNC_ARGS *)

- ea: `0x18001e428`
- end: `0x18001e584`
- name: `?WriteInstallersHashBuffer@@YAXPEAUDIRECTORY_SCAN_FUNC_ARGS@@@Z`
- size: `348`
- prototype: `void __fastcall(struct DIRECTORY_SCAN_FUNC_ARGS *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001b160`

## callees

- `0x1800010b0`
- `0x18000249c`
- `0x180005c94`
- `0x18001e428`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001e528`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001e528`

## pseudocode

```c
void __fastcall WriteInstallersHashBuffer(struct DIRECTORY_SCAN_FUNC_ARGS *a1)
{
  int v1; // r8d
  unsigned int v3; // edi
  int v4; // r8d
  int v5; // r9d
  __int64 v6; // rcx
  __int16 v7; // ax
  void *v8; // rcx
  __int64 v9; // [rsp+60h] [rbp+7h] BYREF
  __int64 v10; // [rsp+68h] [rbp+Fh] BYREF
  __int16 v11; // [rsp+70h] [rbp+17h]
  __int64 v12; // [rsp+78h] [rbp+1Fh] BYREF
  __int16 v13; // [rsp+80h] [rbp+27h]
  __int16 v14; // [rsp+C0h] [rbp+67h] BYREF
  __int16 v15; // [rsp+C8h] [rbp+6Fh] BYREF
  int v16; // [rsp+D0h] [rbp+77h] BYREF
  char *v17; // [rsp+D8h] [rbp+7Fh] BYREF

  v1 = *((unsigned __int16 *)a1 + 60);
  if ( (_WORD)v1 )
  {
    v3 = *((_DWORD *)a1 + 40) * v1;
    if ( (unsigned int)dword_180040010 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180040010, 0x400000000000LL) )
    {
      v6 = *((_QWORD *)a1 + 23);
      v14 = *((_WORD *)a1 + 40);
      v7 = -1;
      if ( v3 <= 0xFFFF )
        v7 = v3;
      v11 = v7;
      v12 = *((_QWORD *)a1 + 18);
      v17 = (char *)a1 + 128;
      v16 = *((_DWORD *)a1 + 40);
      v10 = v6;
      v13 = v4;
      v15 = v4;
      v9 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperArray<8>,_tlgWrapperArray<1>,_tlgWrapperByVal<2>>(
        v6,
        (unsigned int)&byte_18003798F,
        v4,
        v5,
        (__int64)&v9,
        (__int64)&v15,
        (__int64)&v16,
        (__int64)&v17,
        (__int64)&v12,
        (__int64)&v10,
        (__int64)&v14);
    }
    Sleep(0x28u);
    v8 = (void *)*((_QWORD *)a1 + 18);
    *((_WORD *)a1 + 60) = 0;
    memset_0(v8, 0, 0x1F40u);
    memset_0(*((void **)a1 + 23), 0, v3);
    memset_0(*((void **)a1 + 17), 0, *((unsigned __int16 *)a1 + 65));
    *((_WORD *)a1 + 64) = 0;
    *((_WORD *)a1 + 40) = 0;
  }
}

```

## disassembly

```asm
0x18001e428  push    rbp
0x18001e42a  push    rbx
0x18001e42b  push    rsi
0x18001e42c  push    rdi
0x18001e42d  lea     rbp, [rsp-3Fh]
0x18001e432  sub     rsp, 98h
0x18001e439  movzx   r8d, word ptr [rcx+78h]
0x18001e43e  xor     esi, esi
0x18001e440  mov     rbx, rcx
0x18001e443  test    r8w, r8w
0x18001e447  jz      loc_18001E578
0x18001e44d  mov     eax, cs:dword_180040010
0x18001e453  mov     edi, r8d
0x18001e456  imul    edi, [rcx+0A0h]
0x18001e45d  cmp     eax, 5
0x18001e460  jbe     loc_18001E523
0x18001e466  mov     rdx, 400000000000h
0x18001e470  lea     rcx, dword_180040010
0x18001e477  call    _tlgKeywordOn
0x18001e47c  test    al, al
0x18001e47e  jz      loc_18001E523
0x18001e484  movzx   eax, word ptr [rbx+50h]
0x18001e488  mov     rcx, [rbx+0B8h]
0x18001e48f  mov     [rbp+57h+arg_0], ax
0x18001e493  mov     eax, 0FFFFh
0x18001e498  cmp     edi, eax
0x18001e49a  ja      short loc_18001E49F
0x18001e49c  movzx   eax, di
0x18001e49f  mov     [rbp+57h+var_40], ax
0x18001e4a3  lea     rdx, byte_18003798F
0x18001e4aa  mov     rax, [rbx+90h]
0x18001e4b1  mov     [rbp+57h+var_38], rax
0x18001e4b5  lea     rax, [rbx+80h]
0x18001e4bc  mov     [rbp+57h+arg_18], rax
0x18001e4c0  mov     eax, [rbx+0A0h]
0x18001e4c6  mov     [rbp+57h+arg_10], eax
0x18001e4c9  lea     rax, [rbp+57h+arg_0]
0x18001e4cd  mov     [rsp+0B0h+var_60], rax
0x18001e4d2  lea     rax, [rbp+57h+var_48]
0x18001e4d6  mov     [rsp+0B0h+var_68], rax
0x18001e4db  lea     rax, [rbp+57h+var_38]
0x18001e4df  mov     [rsp+0B0h+var_70], rax
0x18001e4e4  lea     rax, [rbp+57h+arg_18]
0x18001e4e8  mov     [rsp+0B0h+var_78], rax
0x18001e4ed  lea     rax, [rbp+57h+arg_10]
0x18001e4f1  mov     [rsp+0B0h+var_80], rax
0x18001e4f6  lea     rax, [rbp+57h+arg_8]
0x18001e4fa  mov     [rsp+0B0h+var_88], rax
0x18001e4ff  lea     rax, [rbp+57h+var_50]
0x18001e503  mov     [rsp+0B0h+var_90], rax
0x18001e508  mov     [rbp+57h+var_48], rcx
0x18001e50c  mov     [rbp+57h+var_30], r8w
0x18001e511  mov     [rbp+57h+arg_8], r8w
0x18001e516  mov     [rbp+57h+var_50], 1000000h
0x18001e51e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapperArray@$07@@U?$_tlgWrapperArray@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapperArray@$07@@AEBU?$_tlgWrapperArray@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperArray<8>,_tlgWrapperArray<1>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperArray<8> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<2> const &)
0x18001e523  mov     ecx, 28h ; '('; dwMilliseconds
0x18001e528  call    cs:__imp_Sleep
0x18001e52e  mov     rcx, [rbx+90h]; void *
0x18001e535  xor     edx, edx; Val
0x18001e537  mov     r8d, 1F40h; Size
0x18001e53d  mov     [rbx+78h], si
0x18001e541  call    memset_0
0x18001e546  mov     rcx, [rbx+0B8h]; void *
0x18001e54d  xor     edx, edx; Val
0x18001e54f  mov     r8d, edi; Size
0x18001e552  call    memset_0
0x18001e557  movzx   r8d, word ptr [rbx+82h]; Size
0x18001e55f  xor     edx, edx; Val
0x18001e561  mov     rcx, [rbx+88h]; void *
0x18001e568  call    memset_0
0x18001e56d  mov     [rbx+80h], si
0x18001e574  mov     [rbx+50h], si
0x18001e578  add     rsp, 98h
0x18001e57f  pop     rdi
0x18001e580  pop     rsi
0x18001e581  pop     rbx
0x18001e582  pop     rbp
0x18001e583  retn
```
