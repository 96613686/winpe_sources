# CSubscriptionItem::NotifyChanged(void)

- ea: `0x180015fd0`
- end: `0x1800160b9`
- name: `?NotifyChanged@CSubscriptionItem@@UEAAJXZ`
- size: `233`
- prototype: `__int64 __fastcall(CSubscriptionItem *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x18000c740`
- `0x180015fd0`
- `0x18001c384`
- `0x18001d420`
- `0x18002924e`
- `0x180029280`
- `0x180029310`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180016053`
- `ole32!CoTaskMemAlloc` at `0x180016053`
- `ole32!CoTaskMemFree` at `0x180016095`
- `ole32!CoTaskMemFree` at `0x180016095`

## pseudocode

```c
__int64 __fastcall CSubscriptionItem::NotifyChanged(CSubscriptionItem *this)
{
  int v2; // ebp
  USHORT v3; // bx
  ITEMIDLIST *v4; // rax
  ITEMIDLIST *v5; // rdi
  unsigned int v7[4]; // [rsp+20h] [rbp-15D8h] BYREF
  _BYTE v8[5520]; // [rsp+30h] [rbp-15C8h] BYREF

  v7[0] = 0;
  memset_0(v8, 0, sizeof(v8));
  v2 = LoadWithCookie(0, (struct OOEBuf *)v8, v7, (struct _GUID *)((char *)this + 12));
  if ( v2 >= 0 && v7[0] <= 0xFFFF )
  {
    v3 = LOWORD(v7[0]) + 224;
    if ( (unsigned __int16)(LOWORD(v7[0]) + 224) >= LOWORD(v7[0]) && (unsigned __int64)v3 + 2 >= v3 )
    {
      v4 = (ITEMIDLIST *)CoTaskMemAlloc(v3 + 2LL);
      v5 = v4;
      if ( v4 )
      {
        memset_0(v4, 0, v3 + 2LL);
        v5->mkid.cb = v3;
        *(_WORD *)v5->mkid.abID = 29701;
        CopyToMyPooe(v8, v5[2].mkid.abID);
        GenerateEvent(0x2000, v5);
        CoTaskMemFree(v5);
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180015fd0  push    rbx
0x180015fd2  push    rbp
0x180015fd3  push    rsi
0x180015fd4  push    rdi
0x180015fd5  mov     eax, 15D8h
0x180015fda  call    _alloca_probe
0x180015fdf  sub     rsp, rax
0x180015fe2  mov     rax, cs:__security_cookie
0x180015fe9  xor     rax, rsp
0x180015fec  mov     [rsp+15F8h+var_38], rax
0x180015ff4  mov     rbx, rcx
0x180015ff7  mov     [rsp+15F8h+var_15D8], 0
0x180015fff  lea     rcx, [rsp+15F8h+var_15C8]; void *
0x180016004  xor     edx, edx; Val
0x180016006  mov     r8d, 1590h; Size
0x18001600c  call    memset_0
0x180016011  lea     r9, [rbx+0Ch]; struct _GUID *
0x180016015  xor     ecx, ecx; psz2
0x180016017  lea     r8, [rsp+15F8h+var_15D8]; unsigned int *
0x18001601c  lea     rdx, [rsp+15F8h+var_15C8]; struct OOEBuf *
0x180016021  call    ?LoadWithCookie@@YAJPEBGPEAUOOEBuf@@PEAKPEAU_GUID@@@Z; LoadWithCookie(ushort const *,OOEBuf *,ulong *,_GUID *)
0x180016026  mov     ebp, eax
0x180016028  test    eax, eax
0x18001602a  js      short loc_18001609B
0x18001602c  mov     ecx, [rsp+15F8h+var_15D8]
0x180016030  cmp     ecx, 0FFFFh
0x180016036  ja      short loc_18001609B
0x180016038  mov     ebx, 0E0h
0x18001603d  add     ebx, ecx
0x18001603f  cmp     bx, cx
0x180016042  jb      short loc_18001609B
0x180016044  movzx   eax, bx
0x180016047  lea     rsi, [rax+2]
0x18001604b  cmp     rsi, rax
0x18001604e  jb      short loc_18001609B
0x180016050  mov     rcx, rsi; cb
0x180016053  call    cs:__imp_CoTaskMemAlloc
0x180016059  mov     rdi, rax
0x18001605c  test    rax, rax
0x18001605f  jz      short loc_18001609B
0x180016061  mov     r8, rsi; Size
0x180016064  xor     edx, edx; Val
0x180016066  mov     rcx, rax; void *
0x180016069  call    memset_0
0x18001606e  lea     rdx, [rdi+8]
0x180016072  mov     [rdi], bx
0x180016075  lea     rcx, [rsp+15F8h+var_15C8]
0x18001607a  mov     word ptr [rdi+2], 7405h
0x180016080  call    CopyToMyPooe
0x180016085  mov     rdx, rdi; pidl2
0x180016088  mov     ecx, 2000h; wEventId
0x18001608d  call    _GenerateEvent
0x180016092  mov     rcx, rdi; pv
0x180016095  call    cs:__imp_CoTaskMemFree
0x18001609b  mov     eax, ebp
0x18001609d  mov     rcx, [rsp+15F8h+var_38]
0x1800160a5  xor     rcx, rsp; StackCookie
0x1800160a8  call    __security_check_cookie
0x1800160ad  add     rsp, 15D8h
0x1800160b4  pop     rdi
0x1800160b5  pop     rsi
0x1800160b6  pop     rbp
0x1800160b7  pop     rbx
0x1800160b8  retn
```
