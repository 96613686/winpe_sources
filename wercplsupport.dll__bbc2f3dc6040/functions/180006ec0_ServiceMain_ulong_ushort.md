# ServiceMain(ulong,ushort * *)

- ea: `0x180006ec0`
- end: `0x180006f7d`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `189`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180002850`
- `0x180006c3c`
- `0x180006c9c`
- `0x180006ec0`
- `0x18000773c`

## pseudocode

```c
void __fastcall ServiceMain(unsigned int a1, unsigned __int16 **a2)
{
  _QWORD *v3; // rcx
  __int64 i; // rbx
  int v6; // eax

  v3 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_42a1f46a1ffc3dae14aad533fcb30511_Traceguids);
      v3 = WPP_GLOBAL_Control;
    }
    for ( i = 0; (unsigned int)i < a1; i = (unsigned int)(i + 1) )
    {
      if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 4) != 0 )
      {
        WPP_SF_S(v3[2], 15, WPP_42a1f46a1ffc3dae14aad533fcb30511_Traceguids, a2[i]);
        v3 = WPP_GLOBAL_Control;
      }
    }
  }
  v6 = CWerCplSupportService::Start(&CWerCplSupportService::ms_instance);
  if ( v6 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_42a1f46a1ffc3dae14aad533fcb30511_Traceguids, (unsigned int)v6);
}

```

## disassembly

```asm
0x180006ec0  push    rbx
0x180006ec2  push    rbp
0x180006ec3  push    rsi
0x180006ec4  push    rdi
0x180006ec5  sub     rsp, 28h
0x180006ec9  mov     edi, ecx
0x180006ecb  lea     rbp, WPP_GLOBAL_Control
0x180006ed2  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ed9  mov     rsi, rdx
0x180006edc  test    byte ptr [rcx+1Ch], 4
0x180006ee0  jz      short loc_180006F3A
0x180006ee2  cmp     rcx, rbp
0x180006ee5  jz      short loc_180006F03
0x180006ee7  mov     rcx, [rcx+10h]
0x180006eeb  lea     r8, WPP_42a1f46a1ffc3dae14aad533fcb30511_Traceguids
0x180006ef2  mov     edx, 0Eh
0x180006ef7  call    WPP_SF_
0x180006efc  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f03  xor     ebx, ebx
0x180006f05  test    edi, edi
0x180006f07  jz      short loc_180006F3A
0x180006f09  cmp     rcx, rbp
0x180006f0c  jz      short loc_180006F34
0x180006f0e  test    byte ptr [rcx+1Ch], 4
0x180006f12  jz      short loc_180006F34
0x180006f14  mov     r9, [rsi+rbx*8]
0x180006f18  lea     r8, WPP_42a1f46a1ffc3dae14aad533fcb30511_Traceguids
0x180006f1f  mov     rcx, [rcx+10h]
0x180006f23  mov     edx, 0Fh
0x180006f28  call    WPP_SF_S
0x180006f2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f34  inc     ebx
0x180006f36  cmp     ebx, edi
0x180006f38  jb      short loc_180006F09
0x180006f3a  lea     rcx, ?ms_instance@CWerCplSupportService@@0V1@A; this
0x180006f41  call    ?Start@CWerCplSupportService@@QEAAJXZ; CWerCplSupportService::Start(void)
0x180006f46  test    eax, eax
0x180006f48  jns     short loc_180006F74
0x180006f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f51  cmp     rcx, rbp
0x180006f54  jz      short loc_180006F74
0x180006f56  test    byte ptr [rcx+1Ch], 1
0x180006f5a  jz      short loc_180006F74
0x180006f5c  mov     rcx, [rcx+10h]
0x180006f60  lea     r8, WPP_42a1f46a1ffc3dae14aad533fcb30511_Traceguids
0x180006f67  mov     edx, 10h
0x180006f6c  mov     r9d, eax
0x180006f6f  call    WPP_SF_d
0x180006f74  add     rsp, 28h
0x180006f78  pop     rdi
0x180006f79  pop     rsi
0x180006f7a  pop     rbp
0x180006f7b  pop     rbx
0x180006f7c  retn
```
