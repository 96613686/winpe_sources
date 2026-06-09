# CWerComStore::Init(tlx::unique_any<tlx::handle_traits<void *,void (void *),&WerpCloseStore(void *),0>>)

- ea: `0x18000bcfc`
- end: `0x18000bd83`
- name: `?Init@CWerComStore@@QEAAJV?$unique_any@U?$handle_traits@PEAX$$A6AXPEAX@Z$1?WerpCloseStore@@YAX0@Z$0A@@tlx@@@tlx@@@Z`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008208`
- `0x180008420`

## callees

- `0x180002850`
- `0x18000bcfc`

## import_xrefs

- `wer!WerpCloseStore` at `0x18000bd46`
- `wer!WerpCloseStore` at `0x18000bd67`
- `wer!WerpCloseStore` at `0x18000bd75`
- `wer!WerpCloseStore` at `0x18000bd46`
- `wer!WerpCloseStore` at `0x18000bd67`
- `wer!WerpCloseStore` at `0x18000bd75`

## pseudocode

```c
__int64 __fastcall CWerComStore::Init(__int64 a1, __int64 *a2)
{
  __int64 v4; // rdx
  __int64 v6; // rcx

  v4 = *a2;
  if ( v4 )
  {
    *a2 = 0;
    v6 = *(_QWORD *)(a1 + 32);
    *(_QWORD *)(a1 + 32) = v4;
    if ( v6 )
      WerpCloseStore();
    if ( *a2 )
      WerpCloseStore();
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
    if ( *a2 )
      WerpCloseStore();
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000bcfc  push    rbx
0x18000bcfe  sub     rsp, 20h
0x18000bd02  mov     rbx, rdx
0x18000bd05  mov     rax, rcx
0x18000bd08  mov     rdx, [rdx]
0x18000bd0b  test    rdx, rdx
0x18000bd0e  jnz     short loc_18000BD53
0x18000bd10  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd17  lea     rax, WPP_GLOBAL_Control
0x18000bd1e  cmp     rcx, rax
0x18000bd21  jz      short loc_18000BD3E
0x18000bd23  test    byte ptr [rcx+1Ch], 1
0x18000bd27  jz      short loc_18000BD3E
0x18000bd29  mov     rcx, [rcx+10h]
0x18000bd2d  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000bd34  mov     edx, 54h ; 'T'
0x18000bd39  call    WPP_SF_
0x18000bd3e  mov     rcx, [rbx]
0x18000bd41  test    rcx, rcx
0x18000bd44  jz      short loc_18000BD4C
0x18000bd46  call    cs:__imp_WerpCloseStore
0x18000bd4c  mov     eax, 80070057h
0x18000bd51  jmp     short loc_18000BD7D
0x18000bd53  mov     qword ptr [rbx], 0
0x18000bd5a  mov     rcx, [rcx+20h]
0x18000bd5e  mov     [rax+20h], rdx
0x18000bd62  test    rcx, rcx
0x18000bd65  jz      short loc_18000BD6D
0x18000bd67  call    cs:__imp_WerpCloseStore
0x18000bd6d  mov     rcx, [rbx]
0x18000bd70  test    rcx, rcx
0x18000bd73  jz      short loc_18000BD7B
0x18000bd75  call    cs:__imp_WerpCloseStore
0x18000bd7b  xor     eax, eax
0x18000bd7d  add     rsp, 20h
0x18000bd81  pop     rbx
0x18000bd82  retn
```
