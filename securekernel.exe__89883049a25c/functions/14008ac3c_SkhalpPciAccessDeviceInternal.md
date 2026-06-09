# SkhalpPciAccessDeviceInternal

- ea: `0x14008ac3c`
- end: `0x14008aecc`
- name: `SkhalpPciAccessDeviceInternal`
- size: `656`
- prototype: `__int64 __fastcall(int, int, int, int, char, char, ULONG_PTR, size_t Size, void *)`
- caller_count: `28`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140089138`
- `0x14008b290`
- `0x14008b580`
- `0x14008ba64`
- `0x14008bdf4`
- `0x14008c6dc`
- `0x14008c934`
- `0x14008ca3c`
- `0x14008cb24`
- `0x14008cc60`
- `0x14008cec8`
- `0x14008cfe0`
- `0x14008d24c`
- `0x14008d3cc`
- `0x14008d690`
- `0x14008dbdc`
- `0x14008dce0`
- `0x14008df44`
- `0x14008e164`
- `0x1400907e8`
- `0x140091154`
- `0x14009147c`
- `0x1400915ac`
- `0x140091854`
- `0x140091908`
- `0x140091a50`
- `0x140091b04`
- `0x140091bb0`

## callees

- `0x1400119c4`
- `0x140082760`
- `0x140082a60`
- `0x14008ac3c`
- `0x14008bfe0`
- `0x14008c0b4`
- `0x1400915ac`
- `0x14009170c`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkhalpPciAccessDeviceInternal(
        char a1,
        char a2,
        unsigned int a3,
        unsigned __int8 a4,
        unsigned __int8 a5,
        unsigned __int8 a6,
        ULONG_PTR a7,
        size_t Size,
        _WORD *a9)
{
  __int64 v9; // rbp
  unsigned int i; // r10d
  __int64 v14; // r9
  unsigned __int8 v15; // r13
  int v16; // r8d
  __int64 v17; // rcx
  signed __int64 v18; // rbx
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 LocalTemporaryMapping; // r10
  _WORD *v23; // rdx
  __int64 v24; // r9
  unsigned int v25; // r11d
  __int64 v26; // rcx
  unsigned int v27; // ecx
  __int64 v28; // rcx
  unsigned int v29; // ecx
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r9
  int Request; // eax
  int BugCheckParameter4; // [rsp+20h] [rbp-88h]
  int v37; // [rsp+28h] [rbp-80h]
  _BYTE v38[88]; // [rsp+50h] [rbp-58h] BYREF

  v9 = a4;
  v38[0] = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= SkhalPciMcfgTableCount )
      goto LABEL_31;
    v14 = 16LL * i;
    if ( a3 == *(unsigned __int16 *)(v14 + SkhalPciMcfgTable + 52)
      && (unsigned __int8)v9 >= *(_BYTE *)(v14 + SkhalPciMcfgTable + 54)
      && (unsigned __int8)v9 <= *(_BYTE *)(v14 + SkhalPciMcfgTable + 55) )
    {
      break;
    }
  }
  v15 = a5;
  v16 = a6;
  v17 = a5 + 32 * v9;
  v18 = *(_QWORD *)(v14 + SkhalPciMcfgTable + 44) + ((a6 + 8 * v17) << 12);
  if ( v18 )
  {
    if ( a2 )
    {
      LOBYTE(v14) = a5;
      LOBYTE(v17) = a1;
      LOBYTE(v16) = v9;
      v19 = SkhalpPciPreProcessWriteRequest(v17, a3, v16, v14, a6, a7, Size, (__int64)a9);
      if ( v19 < 0 )
        SkeBugCheckEx(0xC0u, v19, 0x4766634D000002DFuLL, v18, (unsigned int)a7);
    }
    SkhalpPciAcquireConfigLock(v38);
    LocalTemporaryMapping = SkmmCreateLocalTemporaryMapping(v20, v18 >> 12, 1058);
    v23 = a9;
    v24 = (unsigned int)Size;
    v25 = a7;
    if ( a2 )
    {
      if ( (_DWORD)Size )
      {
        do
        {
          v21 = v25;
          v26 = (v24 & 3) + 4LL * (v25 & 3);
          if ( *((_BYTE *)PCIDeref + v26) )
          {
            if ( *((_BYTE *)PCIDeref + v26) == 2 )
            {
              v27 = 2;
              *(_WORD *)(v25 + LocalTemporaryMapping) = *v23;
            }
            else
            {
              v27 = 1;
              *(_BYTE *)(v25 + LocalTemporaryMapping) = *(_BYTE *)v23;
            }
          }
          else
          {
            v27 = 4;
            *(_DWORD *)(v25 + LocalTemporaryMapping) = *(_DWORD *)v23;
          }
          v25 += v27;
          v23 = (_WORD *)((char *)v23 + v27);
          v24 = (unsigned int)v24 - v27;
        }
        while ( (_DWORD)v24 );
LABEL_27:
        v15 = a5;
      }
    }
    else if ( (_DWORD)Size )
    {
      do
      {
        v21 = v25;
        v28 = (v24 & 3) + 4LL * (v25 & 3);
        if ( *((_BYTE *)PCIDeref + v28) )
        {
          if ( *((_BYTE *)PCIDeref + v28) == 2 )
          {
            v29 = 2;
            *v23 = *(_WORD *)(v25 + LocalTemporaryMapping);
          }
          else
          {
            v29 = 1;
            *(_BYTE *)v23 = *(_BYTE *)(v25 + LocalTemporaryMapping);
          }
        }
        else
        {
          v29 = 4;
          *(_DWORD *)v23 = *(_DWORD *)(v25 + LocalTemporaryMapping);
        }
        v25 += v29;
        v23 = (_WORD *)((char *)v23 + v29);
        v24 = (unsigned int)v24 - v29;
      }
      while ( (_DWORD)v24 );
      goto LABEL_27;
    }
    SkmmReleaseLocalTemporaryMapping(LocalTemporaryMapping, v23, v21, v24);
    LOBYTE(v30) = v38[0];
    SkhalpPciReleaseConfigLock(v30);
    if ( !a2 )
    {
      LOBYTE(v33) = v9;
      LOBYTE(v31) = v38[0];
      LOBYTE(v32) = a1;
      LOBYTE(v37) = a6;
      LOBYTE(BugCheckParameter4) = v15;
      Request = SkhalpPciPostProcessReadRequest(v32, v31, a3, v33, BugCheckParameter4, v37);
      if ( Request < 0 )
        SkeBugCheckEx(0xC0u, Request, 0x4766634D00000318uLL, v18, (unsigned int)a7);
    }
    return 0;
  }
LABEL_31:
  if ( !a2 )
    memset_0(a9, 255, (unsigned int)Size);
  return 0;
}

```

## disassembly

```asm
0x14008ac3c  mov     [rsp+arg_0], cl
0x14008ac40  push    rbx
0x14008ac41  push    rbp
0x14008ac42  push    rsi
0x14008ac43  push    rdi
0x14008ac44  push    r12
0x14008ac46  push    r13
0x14008ac48  push    r14
0x14008ac4a  push    r15
0x14008ac4c  sub     rsp, 68h
0x14008ac50  movzx   ebp, r9b
0x14008ac54  mov     r12d, r8d
0x14008ac57  mov     r14b, dl
0x14008ac5a  mov     [rsp+0A8h+var_58], 0
0x14008ac5f  mov     r11b, cl
0x14008ac62  xor     r10d, r10d
0x14008ac65  cmp     r10d, cs:SkhalPciMcfgTableCount
0x14008ac6c  jnb     loc_14008AE99
0x14008ac72  mov     rdx, cs:SkhalPciMcfgTable
0x14008ac79  mov     r9d, r10d
0x14008ac7c  shl     r9, 4
0x14008ac80  movzx   eax, word ptr [r9+rdx+34h]
0x14008ac86  cmp     r12d, eax
0x14008ac89  jnz     short loc_14008AC99
0x14008ac8b  cmp     bpl, [r9+rdx+36h]
0x14008ac90  jb      short loc_14008AC99
0x14008ac92  cmp     bpl, [r9+rdx+37h]
0x14008ac97  jbe     short loc_14008AC9E
0x14008ac99  inc     r10d
0x14008ac9c  jmp     short loc_14008AC65
0x14008ac9e  movzx   r13d, [rsp+0A8h+arg_20]
0x14008aca7  mov     rcx, rbp
0x14008acaa  movzx   r8d, [rsp+0A8h+arg_28]
0x14008acb3  shl     rcx, 5
0x14008acb7  add     rcx, r13
0x14008acba  lea     rbx, [r8+rcx*8]
0x14008acbe  shl     rbx, 0Ch
0x14008acc2  add     rbx, [r9+rdx+2Ch]
0x14008acc7  jz      loc_14008AE99
0x14008accd  mov     r15, [rsp+0A8h+arg_40]
0x14008acd5  mov     esi, dword ptr [rsp+0A8h+Size]
0x14008acdc  mov     edi, dword ptr [rsp+0A8h+arg_30]
0x14008ace3  test    r14b, r14b
0x14008ace6  jz      short loc_14008AD2F
0x14008ace8  mov     [rsp+0A8h+var_70], r15
0x14008aced  mov     r9b, r13b
0x14008acf0  mov     [rsp+0A8h+var_78], esi
0x14008acf4  mov     edx, r12d
0x14008acf7  mov     [rsp+0A8h+var_80], edi
0x14008acfb  mov     cl, r11b
0x14008acfe  mov     byte ptr [rsp+0A8h+BugCheckParameter4], r8b
0x14008ad03  mov     r8b, bpl
0x14008ad06  call    SkhalpPciPreProcessWriteRequest
0x14008ad0b  test    eax, eax
0x14008ad0d  jns     short loc_14008AD2F
0x14008ad0f  movsxd  rdx, eax; BugCheckParameter1
0x14008ad12  mov     r9, rbx; BugCheckParameter3
0x14008ad15  mov     ecx, 0C0h; BugCheckCode
0x14008ad1a  mov     [rsp+0A8h+BugCheckParameter4], rdi; BugCheckParameter4
0x14008ad1f  mov     r8, 4766634D000002DFh; BugCheckParameter2
0x14008ad29  call    SkeBugCheckEx
0x14008ad2f  lea     rcx, [rsp+0A8h+var_58]
0x14008ad34  call    SkhalpPciAcquireConfigLock
0x14008ad39  mov     rdx, rbx
0x14008ad3c  mov     r8d, 422h
0x14008ad42  sar     rdx, 0Ch
0x14008ad46  call    SkmmCreateLocalTemporaryMapping
0x14008ad4b  mov     r10, rax
0x14008ad4e  mov     rdx, r15
0x14008ad51  mov     r9d, esi
0x14008ad54  mov     r11d, edi
0x14008ad57  test    r14b, r14b
0x14008ad5a  jz      short loc_14008ADC5
0x14008ad5c  test    esi, esi
0x14008ad5e  jz      loc_14008AE30
0x14008ad64  lea     r13, PCIDeref
0x14008ad6b  mov     ecx, r11d
0x14008ad6e  mov     eax, r9d
0x14008ad71  and     eax, 3
0x14008ad74  mov     r8d, r11d
0x14008ad77  and     ecx, 3
0x14008ad7a  lea     rcx, [rax+rcx*4]
0x14008ad7e  movzx   eax, byte ptr [rcx+r13]
0x14008ad83  test    eax, eax
0x14008ad85  jz      short loc_14008ADAB
0x14008ad87  sub     eax, 1
0x14008ad8a  jz      short loc_14008AD9E
0x14008ad8c  cmp     eax, 1
0x14008ad8f  jnz     short loc_14008AD9E
0x14008ad91  lea     ecx, [rax+1]
0x14008ad94  movzx   eax, word ptr [rdx]
0x14008ad97  mov     [r8+r10], ax
0x14008ad9c  jmp     short loc_14008ADB6
0x14008ad9e  mov     al, [rdx]
0x14008ada0  mov     ecx, 1
0x14008ada5  mov     [r8+r10], al
0x14008ada9  jmp     short loc_14008ADB6
0x14008adab  mov     eax, [rdx]
0x14008adad  mov     ecx, 4
0x14008adb2  mov     [r8+r10], eax
0x14008adb6  mov     eax, ecx
0x14008adb8  add     r11d, ecx
0x14008adbb  add     rdx, rax
0x14008adbe  sub     r9d, ecx
0x14008adc1  jnz     short loc_14008AD6B
0x14008adc3  jmp     short loc_14008AE28
0x14008adc5  test    esi, esi
0x14008adc7  jz      short loc_14008AE30
0x14008adc9  lea     r13, PCIDeref
0x14008add0  mov     ecx, r11d
0x14008add3  mov     eax, r9d
0x14008add6  and     eax, 3
0x14008add9  mov     r8d, r11d
0x14008addc  and     ecx, 3
0x14008addf  lea     rcx, [rax+rcx*4]
0x14008ade3  movzx   eax, byte ptr [rcx+r13]
0x14008ade8  test    eax, eax
0x14008adea  jz      short loc_14008AE10
0x14008adec  sub     eax, 1
0x14008adef  jz      short loc_14008AE03
0x14008adf1  cmp     eax, 1
0x14008adf4  jnz     short loc_14008AE03
0x14008adf6  lea     ecx, [rax+1]
0x14008adf9  movzx   eax, word ptr [r8+r10]
0x14008adfe  mov     [rdx], ax
0x14008ae01  jmp     short loc_14008AE1B
0x14008ae03  mov     al, [r8+r10]
0x14008ae07  mov     ecx, 1
0x14008ae0c  mov     [rdx], al
0x14008ae0e  jmp     short loc_14008AE1B
0x14008ae10  mov     eax, [r8+r10]
0x14008ae14  mov     ecx, 4
0x14008ae19  mov     [rdx], eax
0x14008ae1b  mov     eax, ecx
0x14008ae1d  add     r11d, ecx
0x14008ae20  add     rdx, rax
0x14008ae23  sub     r9d, ecx
0x14008ae26  jnz     short loc_14008ADD0
0x14008ae28  mov     r13b, [rsp+0A8h+arg_20]
0x14008ae30  mov     rcx, r10
0x14008ae33  call    SkmmReleaseLocalTemporaryMapping
0x14008ae38  mov     cl, [rsp+0A8h+var_58]
0x14008ae3c  call    SkhalpPciReleaseConfigLock
0x14008ae41  test    r14b, r14b
0x14008ae44  jnz     short loc_14008AEB8
0x14008ae46  mov     al, [rsp+0A8h+arg_28]
0x14008ae4d  mov     r9b, bpl
0x14008ae50  mov     dl, [rsp+0A8h+var_58]
0x14008ae54  mov     r8d, r12d
0x14008ae57  mov     cl, [rsp+0A8h+arg_0]
0x14008ae5e  mov     [rsp+0A8h+var_68], r15
0x14008ae63  mov     dword ptr [rsp+0A8h+var_70], esi
0x14008ae67  mov     byte ptr [rsp+0A8h+var_80], al
0x14008ae6b  mov     byte ptr [rsp+0A8h+BugCheckParameter4], r13b
0x14008ae70  call    SkhalpPciPostProcessReadRequest
0x14008ae75  test    eax, eax
0x14008ae77  jns     short loc_14008AEB8
0x14008ae79  movsxd  rdx, eax; BugCheckParameter1
0x14008ae7c  mov     r9, rbx; BugCheckParameter3
0x14008ae7f  mov     ecx, 0C0h; BugCheckCode
0x14008ae84  mov     [rsp+0A8h+BugCheckParameter4], rdi; BugCheckParameter4
0x14008ae89  mov     r8, 4766634D00000318h; BugCheckParameter2
0x14008ae93  call    SkeBugCheckEx
0x14008ae99  test    r14b, r14b
0x14008ae9c  jnz     short loc_14008AEB8
0x14008ae9e  mov     r8d, dword ptr [rsp+0A8h+Size]; Size
0x14008aea6  mov     edx, 0FFh; Val
0x14008aeab  mov     rcx, [rsp+0A8h+arg_40]; void *
0x14008aeb3  call    memset_0
0x14008aeb8  xor     eax, eax
0x14008aeba  add     rsp, 68h
0x14008aebe  pop     r15
0x14008aec0  pop     r14
0x14008aec2  pop     r13
0x14008aec4  pop     r12
0x14008aec6  pop     rdi
0x14008aec7  pop     rsi
0x14008aec8  pop     rbp
0x14008aec9  pop     rbx
0x14008aeca  retn
```
