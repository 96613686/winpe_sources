# GetVerbAsString(_HTTP_VERB)

- ea: `0x18001a15c`
- end: `0x18001a247`
- name: `?GetVerbAsString@@YAPEBDW4_HTTP_VERB@@@Z`
- size: `235`
- prototype: `const char *__fastcall(enum _HTTP_VERB)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x180005e2c`

## callees

- `0x18001a15c`

## string_xrefs

- `0x18001a1a1`: `DELETE`

## pseudocode

```c
const char *__fastcall GetVerbAsString(enum _HTTP_VERB a1)
{
  _QWORD v2[21]; // [rsp+0h] [rbp-51h]

  v2[3] = "OPTIONS";
  v2[4] = "GET";
  v2[5] = "HEAD";
  v2[6] = "POST";
  v2[7] = "PUT";
  v2[8] = "DELETE";
  v2[9] = "TRACE";
  v2[10] = "CONNECT";
  v2[11] = "TRACK";
  v2[12] = "MOVE";
  v2[13] = "COPY";
  v2[14] = "PROPFIND";
  v2[15] = "PROPPATCH";
  v2[16] = "MKCOL";
  v2[17] = "LOCK";
  v2[18] = "UNLOCK";
  v2[19] = "SEARCH";
  if ( (unsigned int)(a1 - 3) > 0x10 )
    return "INVALID";
  else
    return (const char *)v2[a1];
}

```

## disassembly

```asm
0x18001a15c  push    rbp
0x18001a15e  lea     rbp, [rsp-57h]
0x18001a163  sub     rsp, 90h
0x18001a16a  lea     rax, aOptions; "OPTIONS"
0x18001a171  mov     [rbp+57h+var_90], rax
0x18001a175  lea     rax, aGet; "GET"
0x18001a17c  mov     [rbp+57h+var_88], rax
0x18001a180  lea     rax, aHead; "HEAD"
0x18001a187  mov     [rbp+57h+var_80], rax
0x18001a18b  lea     rax, aPost; "POST"
0x18001a192  mov     [rbp+57h+var_78], rax
0x18001a196  lea     rax, aPut; "PUT"
0x18001a19d  mov     [rbp+57h+var_70], rax
0x18001a1a1  lea     rax, aDelete; "DELETE"
0x18001a1a8  mov     [rbp+57h+var_68], rax
0x18001a1ac  lea     rax, aTrace; "TRACE"
0x18001a1b3  mov     [rbp+57h+var_60], rax
0x18001a1b7  lea     rax, aConnect; "CONNECT"
0x18001a1be  mov     [rbp+57h+var_58], rax
0x18001a1c2  lea     rax, aTrack; "TRACK"
0x18001a1c9  mov     [rbp+57h+var_50], rax
0x18001a1cd  lea     rax, aMove_0; "MOVE"
0x18001a1d4  mov     [rbp+57h+var_48], rax
0x18001a1d8  lea     rax, aCopy_0; "COPY"
0x18001a1df  mov     [rbp+57h+var_40], rax
0x18001a1e3  lea     rax, aPropfind_0; "PROPFIND"
0x18001a1ea  mov     [rbp+57h+var_38], rax
0x18001a1ee  lea     rax, aProppatch; "PROPPATCH"
0x18001a1f5  mov     [rbp+57h+var_30], rax
0x18001a1f9  lea     rax, aMkcol_0; "MKCOL"
0x18001a200  mov     [rbp+57h+var_28], rax
0x18001a204  lea     rax, aLock_0; "LOCK"
0x18001a20b  mov     [rbp+57h+var_20], rax
0x18001a20f  lea     rax, aUnlock_0; "UNLOCK"
0x18001a216  mov     [rbp+57h+var_18], rax
0x18001a21a  lea     rax, aSearch; "SEARCH"
0x18001a221  mov     [rbp+57h+var_10], rax
0x18001a225  lea     eax, [rcx-3]
0x18001a228  cmp     eax, 10h
0x18001a22b  ja      short loc_18001A237
0x18001a22d  movsxd  rax, ecx
0x18001a230  mov     rax, [rbp+rax*8+57h+var_A8]
0x18001a235  jmp     short loc_18001A23E
0x18001a237  lea     rax, aInvalid; "INVALID"
0x18001a23e  add     rsp, 90h
0x18001a245  pop     rbp
0x18001a246  retn
```
