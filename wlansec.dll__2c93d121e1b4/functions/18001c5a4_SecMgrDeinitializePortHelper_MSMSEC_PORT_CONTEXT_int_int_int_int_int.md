# SecMgrDeinitializePortHelper(MSMSEC_PORT_CONTEXT *,int,int,int,int,int)

- ea: `0x18001c5a4`
- end: `0x18001c75b`
- name: `?SecMgrDeinitializePortHelper@@YAXPEAUMSMSEC_PORT_CONTEXT@@HHHHH@Z`
- size: `439`
- prototype: `void __usercall(struct MSMSEC_PORT_CONTEXT *@<rcx>, int@<edx>, int@<r8d>, int@<r9d>, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18001c068`
- `0x18001c9ac`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18001c5a4`
- `0x18001c764`
- `0x18001c968`
- `0x18001f1d4`
- `0x180033a54`
- `0x1800354e0`
- `0x180035a44`
- `0x180035ae0`

## import_xrefs

- `MobileNetworking!DeleteReadWriteLock` at `0x18001c6e5`
- `MobileNetworking!DeleteReadWriteLock` at `0x18001c6e5`

## pseudocode

```c
void __fastcall SecMgrDeinitializePortHelper(struct MSMSEC_PORT_CONTEXT *a1, int a2, int a3, int a4, int a5, int a6)
{
  PVOID *v10; // rdi

  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 49, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 68) & 2) != 0 )
      WPP_SF_DDDDDD(
        v10[7],
        50,
        &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids,
        *((unsigned __int8 *)a1 + 302),
        *((unsigned __int8 *)a1 + 303),
        *((unsigned __int8 *)a1 + 304),
        *((unsigned __int8 *)a1 + 305));
  }
  if ( a3 )
    AuthMgrDeinitialize((struct MSMSEC_PORT_CONTEXT *)((char *)a1 + 920));
  if ( a4 )
    KeyMgrDeinitialize(a1);
  if ( a5 )
    KeyCacheDeinitialize((struct MSMSEC_PORT_CONTEXT *)((char *)a1 + 776));
  if ( a6 )
    WpsAuthMgrDeinitialize((struct MSMSEC_PORT_CONTEXT *)((char *)a1 + 1992));
  if ( a2 )
    DeleteReadWriteLock((char *)a1 + 320);
  if ( !*((_DWORD *)a1 + 126) )
    FreePortSendKeys(a1);
  ScrubAndFreeKeyMaterial((char *)a1 + 1176, (char *)a1 + 1168);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 51, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, 0);
}

```

## disassembly

```asm
0x18001c5a4  push    rbx
0x18001c5a6  push    rbp
0x18001c5a7  push    rsi
0x18001c5a8  push    rdi
0x18001c5a9  push    r14
0x18001c5ab  push    r15
0x18001c5ad  sub     rsp, 58h
0x18001c5b1  mov     ebp, r9d
0x18001c5b4  mov     esi, r8d
0x18001c5b7  mov     r14d, edx
0x18001c5ba  mov     rbx, rcx
0x18001c5bd  mov     rdi, cs:WPP_GLOBAL_Control
0x18001c5c4  lea     r15, WPP_GLOBAL_Control
0x18001c5cb  cmp     rdi, r15
0x18001c5ce  jnz     loc_18001C65F
0x18001c5d4  xor     edi, edi
0x18001c5d6  test    esi, esi
0x18001c5d8  jnz     short loc_18001C643
0x18001c5da  test    ebp, ebp
0x18001c5dc  jnz     loc_18001C6F6
0x18001c5e2  cmp     [rsp+88h+arg_20], edi
0x18001c5e9  jnz     short loc_18001C651
0x18001c5eb  cmp     [rsp+88h+arg_28], edi
0x18001c5f2  jz      short loc_18001C600
0x18001c5f4  lea     rcx, [rbx+7C8h]; struct MSMSEC_PORT_WPS_AUTH_CONTEXT *
0x18001c5fb  call    ?WpsAuthMgrDeinitialize@@YAXPEAUMSMSEC_PORT_WPS_AUTH_CONTEXT@@@Z; WpsAuthMgrDeinitialize(MSMSEC_PORT_WPS_AUTH_CONTEXT *)
0x18001c600  test    r14d, r14d
0x18001c603  jnz     loc_18001C6DE
0x18001c609  cmp     [rbx+1F8h], edi
0x18001c60f  jz      loc_18001C724
0x18001c615  lea     rdx, [rbx+490h]
0x18001c61c  lea     rcx, [rdx+8]
0x18001c620  call    ScrubAndFreeKeyMaterial
0x18001c625  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c62c  cmp     rcx, r15
0x18001c62f  jnz     loc_18001C731
0x18001c635  add     rsp, 58h
0x18001c639  pop     r15
0x18001c63b  pop     r14
0x18001c63d  pop     rdi
0x18001c63e  pop     rsi
0x18001c63f  pop     rbp
0x18001c640  pop     rbx
0x18001c641  retn
0x18001c643  lea     rcx, [rbx+398h]; struct MSMSEC_PORT_AUTH_CONTEXT *
0x18001c64a  call    ?AuthMgrDeinitialize@@YAXPEAUMSMSEC_PORT_AUTH_CONTEXT@@@Z; AuthMgrDeinitialize(MSMSEC_PORT_AUTH_CONTEXT *)
0x18001c64f  jmp     short loc_18001C5DA
0x18001c651  lea     rcx, [rbx+308h]; struct MSMSEC_EAPOL_KEY_CACHE *
0x18001c658  call    ?KeyCacheDeinitialize@@YAXPEAUMSMSEC_EAPOL_KEY_CACHE@@@Z; KeyCacheDeinitialize(MSMSEC_EAPOL_KEY_CACHE *)
0x18001c65d  jmp     short loc_18001C5EB
0x18001c65f  test    dword ptr [rdi+44h], 100h
0x18001c666  jnz     loc_18001C703
0x18001c66c  cmp     rdi, r15
0x18001c66f  jz      loc_18001C5D4
0x18001c675  test    byte ptr [rdi+44h], 2
0x18001c679  jz      loc_18001C5D4
0x18001c67f  movzx   ecx, byte ptr [rbx+132h]
0x18001c686  mov     edx, 32h ; '2'
0x18001c68b  movzx   r8d, byte ptr [rbx+131h]
0x18001c693  movzx   eax, byte ptr [rbx+133h]
0x18001c69a  movzx   r10d, byte ptr [rbx+130h]
0x18001c6a2  movzx   r11d, byte ptr [rbx+12Fh]
0x18001c6aa  movzx   r9d, byte ptr [rbx+12Eh]
0x18001c6b2  mov     [rsp+88h+var_48], eax
0x18001c6b6  mov     [rsp+88h+var_50], ecx
0x18001c6ba  mov     rcx, [rdi+38h]
0x18001c6be  mov     [rsp+88h+var_58], r8d
0x18001c6c3  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18001c6ca  mov     [rsp+88h+var_60], r10d
0x18001c6cf  mov     [rsp+88h+var_68], r11d
0x18001c6d4  call    WPP_SF_DDDDDD
0x18001c6d9  jmp     loc_18001C5D4
0x18001c6de  lea     rcx, [rbx+140h]
0x18001c6e5  call    cs:__imp_DeleteReadWriteLock
0x18001c6ec  nop     dword ptr [rax+rax+00h]
0x18001c6f1  jmp     loc_18001C609
0x18001c6f6  mov     rcx, rbx; struct MSMSEC_PORT_CONTEXT *
0x18001c6f9  call    ?KeyMgrDeinitialize@@YAXPEAUMSMSEC_PORT_CONTEXT@@@Z; KeyMgrDeinitialize(MSMSEC_PORT_CONTEXT *)
0x18001c6fe  jmp     loc_18001C5E2
0x18001c703  mov     rcx, [rdi+38h]
0x18001c707  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18001c70e  mov     edx, 31h ; '1'
0x18001c713  call    WPP_SF_
0x18001c718  mov     rdi, cs:WPP_GLOBAL_Control
0x18001c71f  jmp     loc_18001C66C
0x18001c724  mov     rcx, rbx; struct MSMSEC_PORT_CONTEXT *
0x18001c727  call    ?FreePortSendKeys@@YAXPEAUMSMSEC_PORT_CONTEXT@@@Z; FreePortSendKeys(MSMSEC_PORT_CONTEXT *)
0x18001c72c  jmp     loc_18001C615
0x18001c731  test    dword ptr [rcx+44h], 100h
0x18001c738  jz      loc_18001C635
0x18001c73e  mov     rcx, [rcx+38h]
0x18001c742  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18001c749  mov     edx, 33h ; '3'
0x18001c74e  xor     r9d, r9d
0x18001c751  call    WPP_SF_d
0x18001c756  jmp     loc_18001C635
```
