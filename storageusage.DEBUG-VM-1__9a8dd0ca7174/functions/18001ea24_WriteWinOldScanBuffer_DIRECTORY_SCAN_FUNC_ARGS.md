# WriteWinOldScanBuffer(DIRECTORY_SCAN_FUNC_ARGS *)

- ea: `0x18001ea24`
- end: `0x18001eb1a`
- name: `?WriteWinOldScanBuffer@@YAXPEAUDIRECTORY_SCAN_FUNC_ARGS@@@Z`
- size: `246`
- prototype: `void __fastcall(struct DIRECTORY_SCAN_FUNC_ARGS *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001b430`

## callees

- `0x1800010b0`
- `0x1800023d4`
- `0x180005c94`
- `0x18001ea24`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001ead0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001ead0`

## pseudocode

```c
void __fastcall WriteWinOldScanBuffer(struct DIRECTORY_SCAN_FUNC_ARGS *a1)
{
  int v2; // ecx
  int v3; // r8d
  int v4; // r9d
  void *v5; // rcx
  __int64 v6; // [rsp+40h] [rbp-18h] BYREF
  __int16 v7; // [rsp+48h] [rbp-10h]
  __int16 v8; // [rsp+60h] [rbp+8h] BYREF
  char *v9; // [rsp+68h] [rbp+10h] BYREF
  __int64 v10; // [rsp+70h] [rbp+18h] BYREF

  if ( *((_WORD *)a1 + 60) )
  {
    if ( (unsigned int)dword_180040010 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180040010, 0x400000000000LL) )
      {
        v8 = *((_WORD *)a1 + 40);
        v9 = (char *)a1 + 128;
        v6 = *((_QWORD *)a1 + 18);
        v7 = v3;
        v10 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperArray<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<2>>(
          v2,
          (unsigned int)&dword_180037C9C,
          v3,
          v4,
          (__int64)&v10,
          (__int64)&v6,
          (__int64)&v9,
          (__int64)&v8);
      }
    }
    Sleep(0x28u);
    v5 = (void *)*((_QWORD *)a1 + 18);
    *((_WORD *)a1 + 60) = 0;
    memset_0(v5, 0, 0x1F40u);
    memset_0(*((void **)a1 + 17), 0, *((unsigned __int16 *)a1 + 65));
    *((_WORD *)a1 + 64) = 0;
    *((_WORD *)a1 + 40) = 0;
  }
}

```

## disassembly

```asm
0x18001ea24  mov     [rsp+arg_18], rbx
0x18001ea29  push    rdi
0x18001ea2a  sub     rsp, 50h
0x18001ea2e  movzx   r8d, word ptr [rcx+78h]
0x18001ea33  xor     edi, edi
0x18001ea35  mov     rbx, rcx
0x18001ea38  test    r8w, r8w
0x18001ea3c  jz      loc_18001EB0F
0x18001ea42  mov     eax, cs:dword_180040010
0x18001ea48  cmp     eax, 5
0x18001ea4b  jbe     short loc_18001EACB
0x18001ea4d  mov     rdx, 400000000000h
0x18001ea57  lea     rcx, dword_180040010
0x18001ea5e  call    _tlgKeywordOn
0x18001ea63  test    al, al
0x18001ea65  jz      short loc_18001EACB
0x18001ea67  movzx   eax, word ptr [rbx+50h]
0x18001ea6b  lea     rdx, dword_180037C9C
0x18001ea72  mov     [rsp+58h+arg_0], ax
0x18001ea77  lea     rax, [rbx+80h]
0x18001ea7e  mov     [rsp+58h+arg_8], rax
0x18001ea83  mov     rax, [rbx+90h]
0x18001ea8a  mov     [rsp+58h+var_18], rax
0x18001ea8f  lea     rax, [rsp+58h+arg_0]
0x18001ea94  mov     [rsp+58h+var_20], rax
0x18001ea99  lea     rax, [rsp+58h+arg_8]
0x18001ea9e  mov     [rsp+58h+var_28], rax
0x18001eaa3  lea     rax, [rsp+58h+var_18]
0x18001eaa8  mov     [rsp+58h+var_30], rax
0x18001eaad  lea     rax, [rsp+58h+arg_10]
0x18001eab2  mov     [rsp+58h+var_38], rax
0x18001eab7  mov     [rsp+58h+var_10], r8w
0x18001eabd  mov     [rsp+58h+arg_10], 1000000h
0x18001eac6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperArray@$07@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperArray@$07@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperArray<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperArray<8> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<2> const &)
0x18001eacb  mov     ecx, 28h ; '('; dwMilliseconds
0x18001ead0  call    cs:__imp_Sleep
0x18001ead6  mov     rcx, [rbx+90h]; void *
0x18001eadd  xor     edx, edx; Val
0x18001eadf  mov     r8d, 1F40h; Size
0x18001eae5  mov     [rbx+78h], di
0x18001eae9  call    memset_0
0x18001eaee  movzx   r8d, word ptr [rbx+82h]; Size
0x18001eaf6  xor     edx, edx; Val
0x18001eaf8  mov     rcx, [rbx+88h]; void *
0x18001eaff  call    memset_0
0x18001eb04  mov     [rbx+80h], di
0x18001eb0b  mov     [rbx+50h], di
0x18001eb0f  mov     rbx, [rsp+58h+arg_18]
0x18001eb14  add     rsp, 50h
0x18001eb18  pop     rdi
0x18001eb19  retn
```
